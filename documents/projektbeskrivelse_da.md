# Projektbeskrivelse

## Introduktion

OS² oplever en stigende efterspørgsel på løsninger, der kan håndtere data og arbejdsgange omkring data på en effektiv og sikker måde. Ligeledes efterspørges der metoder og værktøjer der kan minimere risisci ved benyttelse af flere specialistleverandører. 

Og det er sandt at der er en række risisci forbundet med at kaste sig ud i sådan et projekt og OS² vil med dette projekt tilbyde at mitigere disse for sine medlemmer og gå forrest med rådgivning om metoder til transparent og effektiv leverandørstyring.

## Rationale

Det er ikke formålstjeneligt, at danske myndigheder belastes økonomisk med udvikling af flere unikke danske datainfrastrukturer, hver gang der skal bruges et nyt dataprodukt.
OS² vil vise, hvordan man kan drage fordel af anerkendt og tidssvarende faglig viden inden for projektledelse.
På den måde kan vi styre vores medlemmer uden om risikable bias som _exceptionalismebias_[¹](#risici-i-projekter) og afledte låse, der kan binde projekter uhensigtsmæssigt til teknologier, leverandører eller enkeltpersoner.
på den måde kan vi i fællesskab undgå at vores medlemmers handlefrihed bliver lammet.

Dette kan løses ved at bygge på internationale open source erfaring med genbrug af open source komponenter der lever op til moderne nationale og internationale arkitekturprincipper[²](#arkitektur).

## Løsningsbeskrivelse

Løsningen skal kunne modtage eller hente data og aflevere dem til et eller flere datamål. I processen skal der understøttes standardiserede arbejdsgange som f.eks godkendelses trin, kald af eksterne snitflader samt både liniære enkelte og flere samtidige databehandlinger. Løsningen skal ikke bindes til et enkelt softwareprojekt eller løsning, men sammensættes så den er genanvendelig på tværs af OS²s projekt portefølje.

## Strategiske forretningsmål

OS² vil med sin rådgivning til projektet arbejde ud fra en række overordnede forretningsmål der leverer værdi til de deltagende medlemmer. Følgende hovedoverskrifter beskriver forretningsmålene:

### 1. 🇪🇺 Digital suverænitet og handlefrihed
### 2. 🐎 Hastighed via genbrug
### 3. 🚀 Effektivitet og talentudvikling
### 4. ⚖️ Neutralitet og samskabelse

## 
## Hvordan vil vi opnå forretningsmålene?

 - Løsningen forankres i os2s versionsstyrede sandkasse der sikrer transparens og samarbejde.
 - Løsningen sammensættes af allerede eksisterende bredt anvendte open source komponenter, der har tilknyttet robuste vedligeholdelses organisationer.
 - Løsningen vil udnytte den internationale erfaring der ligger i CNCFs modenhedsmodeller[³](#modenhedsmodel)
 - Løsningen bygges ud fra best practice principper for moderne skalerbare applikationer[⁴](#12Factor)


 og kommer til at bestå af genbrugelig komponenter. 

 til at drastisk forenkle udviklingen af nye dataprodukter.

 Ved at abstrahere og ensrette den underliggende infrastruktur skal udvikleren kun fokusere på forretningslogik og kan frit vælge blandt alle  Dette gør leverancer ved eksterne leverandører ensartede og hurtigere at lave og sætter barren på et nivau så der åbnes for egenuvikling af dataprodukter blandt de deltagende myndigheders egne digitaliserings medarbejdere. Løsningen stiller ikke krav om kompetencer i enkelte udviklingssprog, men understøtter bredt de mest anvendte moderne udviklingssprog. 


## Hvem vil vi lave det for – hvem er målgruppen?

Målgruppen for projektet er kommunale IT-afdelinger, offentlige institutioner og andre organisationer, der har behov for en fleksibel og skalerbar data pipeline. Projektet vil også være relevant for udviklere og tekniske teams, der arbejder med datahåndtering og integration.

## Hvorfor vil vi gerne lave projektet – hvorfor er der et behov, og hvorfor er projektet løsningen?


fokusere på forretningslogik fremfor infrastruktur, og som kan integreres med forskellige teknologier. Dette vil forbedre ydeevnen, pålideligheden og sikkerheden af applikationer, samtidig med at det giver fleksibilitet og skalerbarhed. 

Projektet vil blive sammensat som en cloud-native løsning med en deklarativ konfiguration, der gør opsætning og vedligeholdelse nemmere. Vi vil anvende flersproget support og indbygget robusthed med automatiske genforsøg, tidsbegrænsninger og kredsløbsafbrydere. For at nå målet vil vi følge en agil udviklingsmetode, hvor vi løbende tester og forbedrer løsningen baseret på feedback fra brugerne.





Hvor skal projektet etableres?

Projektet vil blive etableret i kommunens IT-afdeling, med mulighed for at udvide til andre offentlige institutioner og organisationer, der har behov for en lignende løsning.
Hvordan har vi tænkt os, at projektet skal være/se ud – og hvordan kommer vi derhen?

Projektet vil blive udviklet som en cloud-native løsning med en deklarativ konfiguration, der gør opsætning og vedligeholdelse nemmere. Vi vil anvende flersproget support og indbygget robusthed med automatiske genforsøg, tidsbegrænsninger og kredsløbsafbrydere. For at nå målet vil vi følge en agil udviklingsmetode, hvor vi løbende tester og forbedrer løsningen baseret på feedback fra brugerne.
Hvornår vil vi gennemføre projektet?

Projektet vil blive gennemført over en periode på 12 måneder, med milepæle hver tredje måned for at sikre, at vi er på rette spor og kan justere planen efter behov.
Hvordan sikrer vi den efterfølgende drift af projektet?

Den efterfølgende drift af projektet vil blive sikret gennem løbende vedligeholdelse og support fra kommunens IT-afdeling. Vi vil også etablere en dokumentations- og træningsplan for at sikre, at alle relevante medarbejdere er i stand til at bruge og vedligeholde løsningen.

#### Risici i projekter

- [*Forskningscenter for Offentlig IT, IT University of Copenhagen* - Flyvbjerg, B., & Gardner, D. (2024). Uniqueness Bias: Why It Matters, How to Curb It.](https://pure.itu.dk/da/publications/uniqueness-bias-why-it-matters-how-to-curb-it)
- [*Harward Busines Review* - Flyvbjerg, B., Budzier, A., Christodoulou, M. D., & Zottoli, M. (2025, March). The uniqueness trap. ](https://hbr.org/2025/03/the-uniqueness-trap)

#### Modenhedsmodel

- [*Cloud Native Computing Foundation* - Project Metrics](https://www.cncf.io/project-metrics/)

#### Arkitektur

- [*Digitaliseringsstyrelsen* - Principper og regler for fællesoffentlig digital arkitektur (2025).](https://arkitektur.digst.dk/principper-og-regler)
- [*Opensource.com* - Klein, J. (2021, November 30). Open source and the 12-factor app methodology.](https://opensource.com/article/21/11/open-source-12-factor-app-methodology)

#### 12factor

- [*The Twelve-Factor Manifesto* - Wiggins, A., & Keith, A. (2011). The Twelve-Factor App.](https://github.com/twelve-factor/twelve-factor)

#### Tekniske guides

- [*Microsoft Learn* - Microservices made easy with Dapr](https://learn.microsoft.com/en-us/shows/the-launch-space/microservices-made-easy-with-dapr)

- [*Dapr University* - Dapr 101 & Dapr Workflows](https://www.diagrid.io/dapr-university)