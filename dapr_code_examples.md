## Eksempel på kode med hårde bindinger

```python
import requests
from tenacity import retry, wait_random_exponential, stop_after_attempt
from fleetmanager.logging import logging
from sqlalchemy import create_engine, update
from sqlalchemy.orm import sessionmaker
import xmltodict
from datetime import date, datetime

logger = logging.getLogger(__name__)

# Database setup
DB_NAME = "your_db_name"
DB_PASSWORD = "your_db_password"
DB_USER = "your_db_user"
DB_URL = "your_db_url"
DB_SERVER = "your_db_server"
engine = create_engine(f"{DB_SERVER}://{DB_USER}:{DB_PASSWORD}@{DB_URL}/{DB_NAME}")
Session = sessionmaker(autocommit=False, autoflush=False, bind=engine)

class DuplicatePlateCleverTrack(Exception):
    pass

class TripIdPatchError(Exception):
    pass

@retry(wait=wait_random_exponential(min=1, max=20), stop=stop_after_attempt(6))
def get_vehicles(token: str):
    url = "https://ctpublic.azurewebsites.net/api/vehicles"
    header = {"token": token, "Accept": "application/json"}
    response = requests.get(url, headers=header)
    vehicles = None
    if response.status_code == 200:
        vehicles = response.json()
        save_vehicles_to_db(vehicles)
    return vehicles

def save_vehicles_to_db(vehicles):
    session = Session()
    for vehicle in vehicles:
        plate = extract_plate(vehicle.get("name")) or extract_plate(vehicle.get("deviceType"))
        if plate:
            vehicle_data = {
                "id": vehicle.get("id"),
                "plate": plate,
                "imei": vehicle.get("imei", ""),
                "description": vehicle.get("description", "")
            }
            stmt = update(Cars).where(Cars.id == vehicle_data["id"]).values(vehicle_data)
            session.execute(stmt)
            session.commit()

def extract_plate(name):
    return name.split()[0] if name else None

@retry(wait=wait_random_exponential(min=1, max=20), stop=stop_after_attempt(3))
def get_trips(token: str, start: str, stop: str = None):
    if stop is None:
        stop = date.today()
    url = f"https://ctpublic.azurewebsites.net/api/triplist?start={start}&stop={stop}"
    header = {"token": token, "Accept": "application/json"}
    response = requests.get(url, headers=header)
    trips = None
    if response.status_code == 200:
        trips = response.json()
        return trips.get("trips")
    return trips

@retry(wait=wait_random_exponential(min=1, max=20), stop=stop_after_attempt(3))
def patch_trips(token: str, ids: list[int]):
    url = "https://ctpublic.azurewebsites.net/api/triplist"
    header = {"token": token}
    body = {"tripIDs": ids}
    response = requests.patch(url, json=body, headers=header)
    if response.status_code == 200:
        confirmation = (
            xmltodict.parse(response.content)
            .get("tripListAnswer")
            .get("tripIDs", {})
            .get("d2p1:int", [])
        )
        if isinstance(confirmation, str) and len(ids) == 1:
            confirmation = [confirmation]

        if len(confirmation) != len(ids):
            raise TripIdPatchError(
                f"Returned number of patched ids: {len(confirmation)} did not match the requested: {len(ids)}"
            )

        logger.info(f"Patched {len(ids)} ids.")
        return
    raise TripIdPatchError(
        f"Request did not return 200 response, but {response.status_code} and response {response.content}"
    )

def find_item_plate_list(plate: str, vehicles_list):
    car = list(
        filter(
            lambda car: plate in car.get("name", "")
            or plate in car.get("deviceType", ""),
            vehicles_list,
        )
    )
    if len(car) > 1:
        ids = [a["id"] for a in car]
        raise DuplicatePlateCleverTrack(
            f"There were found multiple vehicles with the plate {plate}, ids: {ids}"
        )
    if car:
        car = dict(car[0])
    else:
        car = {}
    return car
```

## Eksempel på løskoblet kode
```python
from dapr.clients import DaprClient

def invoke_external_api():
    with DaprClient() as d:
        token = d.get_secret("secretstore", "apiToken")["apiToken"]
        response = d.invoke_binding(
            binding_name='externalApiBinding',
            operation='get',
            data='',
            metadata={'Authorization': f'Bearer {token}'}
        )
        d.save_state

```

Snitflade konfiguration
```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: externalApiBinding
spec:
  type: bindings.http
  version: v1
  metadata:
  - name: url
    value: "http://example.com/api"
  - name: schedule
    value: "@daily"
```

```yaml
apiVersion: dapr.io/v1alpha1
kind: Resiliency
metadata:
  name: apiResiliency
spec:
  policies:
    retries:
      default:
        maxRetries: 3
        interval: "1s"
    timeouts:
      default:
        duration: "5s"
scopes:
  - appId: app-id
    policy: default

```

