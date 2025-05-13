Kode
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