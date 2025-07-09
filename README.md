# cbs-regionale-data

## Situatie

CBS Statline wordt in veel data science projecten gebruikt als 'context' informatie, met name ook de [kerncijfers wijken en buurten](https://www.cbs.nl/nl-nl/reeksen/publicatie/kerncijfers-wijken-en-buurten) en alle tabellen onder het thema [Nederland Regionaal](https://www.cbs.nl/nl-nl/dossier/nederland-regionaal).

Terwijl CBS Statline een goede [OData API](https://www.cbs.nl/nl-nl/onze-diensten/open-data/statline-als-open-data) heeft, leert de praktijk dat het toch vaak weer ad-hoc data engineering vergt om de data goed te gebruiken. Daarom willen we als challenge-based project een 'mini-lakehouse' realiseren waarin alle regionale data van CBS makkelijk toegangkelijk en deelbaar is. Dit project bouwt voort op een eerder open soruce project wat iets vergelijkbaars wilde realiseren ([NL Open Data](https://github.com/dataverbinders/nl-open-data)) alleen was destijds DuckDB niet beschikbaar.

## Doelen (klantperspectief)

- Een werkend lakehouse geimplementeerd met moderne Python modules die gebaseerd zijn op Rust (polars, DuckDB, pydantic)
- Een end-to-end pipeline zoals is beschreven in deze [masterclass data engineering](https://anthology-of-data.science/lectures/composable-data-stack.html)
- [DuckLake](https://ducklake.select/) als target engine
- Dimensionaal model met in elk geval
  - Gebiedsindeling gebaseerd op postcode gebieden (PC4, PC5, PC6)
  - Gebiedsindeling gebaseerd op wijken en buurten
  - Mogelijk maken om mapping tussen die twee gebiedsindelingen te maken
  - Gebiedsindeling is een slowly-changing type II dimension vanwege continue gemeentelijke herindeling. De gebruiker moet b.v. een gebiedsindeling op een bepaalde peildatum kunnen kiezen en dat alle data daar naartoe wordt gemapped
  - Basis GIS/polygoon informatie zodat de data als backend gebruikt kan worden voor visualisatie op kaarten
 
## Leerdoelen

- End-to-end Python data engineerin pipelines opzetten die zoveel mogelijk met serverless technieken werken
- Kimball/stermodelering toepassen
- Ervaring opdoen over user-requirements en toegankelijk maken van een lakehouse data product


