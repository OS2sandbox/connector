# Projektbeskrivelse

## Rationale

OS² oplever en stigende efterspørgsel på løsninger, der kan håndtere data og arbejdsgange. De tekniske løsninger findes allerede men flere leverandører peger på udfordringer med at tilbyde genbrug af moderne, distribuerede services til vores medlemmer, uden at omkostningerne stiger uforholdsmæssigt.
Dette kan løses ved at indrage flere specialiserede leverandører i leverancerne, men der er usikkerhed om hvordan risisci minimeres når sådanne flerleverandør scenarier skal lykkes!

Det er sandt at der er en række risisci forbundet med at levere på nye måder og OS² tilbyder derfor at gå forrest med rådgivning om metoder til at minimere risisci og komme i mål med transparente og effektive moderne løsninger.

Det er ikke formålstjeneligt, at danske myndigheder belastes økonomisk med udvikling af flere unikke danske datainfrastrukturer, hver gang der skal bruges et nyt dataprodukt.
OS² vil vise, hvordan man kan drage fordel af anerkendt og tidssvarende faglig viden inden for projektledelse og software udviklings praksis.
På den måde kan vi styre vores medlemmer uden om risikable bias som _exceptionalismebias_[¹](#risici-i-projekter) og afledte låse, der kan binde projekter uhensigtsmæssigt til teknologier, leverandører eller enkeltpersoner.
På den måde kan vi i fællesskab undgå at vores medlemmers handlefrihed bliver lammet.

Dette kan løses ved at bygge på international erfaring med genbrug af open source komponenter der lever op til moderne nationale og internationale arkitekturprincipper[²](#arkitektur).

## Løsningsbeskrivelse

_Løsningen skal kunne modtage behandle og aflevere data til et eller flere datamål. Systemet skal understøtte udveksling af data med andre systemer uden at begrænse myndighedernes handlefrihed._

 I processen skal der understøttes standardiserede arbejdsgange som f.eks godkendelses trin, kald af eksterne snitflader samt både liniære enkelte og flere samtidige databehandlinger. Løsningen skal ikke bindes til et enkelt udviklingssprog eller leverandør, men sammensættes så den er genanvendelig på tværs af OS²s projekt portefølje. 

## Strategiske forretningsmål

OS² vil med sin rådgivning til projektet arbejde ud fra en række overordnede forretningsmål der leverer værdi til de deltagende myndigheder. 

Følgende hovedoverskrifter beskriver forretningsmålene:

### 1. 🇪🇺 Digital suverænitet og handlefrihed
### 2. 🐎 Hastighed via genbrug
### 3. 🚀 Effektivitet og talentudvikling
### 4. ⚖️ Neutralitet og samskabelse

## 
## Hvordan vil vi opnå forretningsmålene?

 - Løsningen forankres i os2s versionsstyrede udviklingsmiljø der sikrer transparens og samarbejde.
 - Løsningen sammensættes af allerede eksisterende bredt anvendte open source komponenter, der har tilknyttet robuste vedligeholdelses organisationer.
 - Løsningen vil udnytte den internationale erfaring der ligger i CNCFs modenhedsmodeller[³](#modenhedsmodel)
 - Løsningen bygges ud fra best practice principper for moderne skalerbare applikationer[⁴](#12Factor)
 - Løsningen bygges med hensyntagen til forretningsudviklere, så den kan abstrahere de tekniske udfordringer der kan være med distribuerede løsninger. 
 - Arkitekturen skal understøtte udvikling af moderne, distribuerede løsninger uden at udvikleren skal bekymre sig om kompleksiteten ved infrastrukturen bagved
 - Løsningen udvikles i fællesskab med andre OS² projekter for at sikre et robust og genbrugeligt resultet

## Leverance

Projektet starter med en simpel PoC der skal kunne leveres inden for 5 uger efter projektstart. PoCen afvikles i et seperat prototype miljø og vil indeholde et enkelt data-forløb for at bevise værdien og stabiliteten i løsningen.
Der er indhentet tilbud på denne PoC.

Accepteres resultatet af PoCen laves der efterfølgende en ny leveranceplan for etablering af en produktionsklar løsning. 
Denne produktmodning er ikke detailplanlagt men vil kunne foregå i iterationer over en periode på 12 måneder, med milepæle hver tredje måned for at sikre, at vi er på rette spor og kan justere planen efter behov. Fokus vil være på produktionsmodning og skalerbarhed med flere dataforløb.

## Noter

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