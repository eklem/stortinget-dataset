# stortinget-dataset
Datasett fra data.stortinget.no for å lage et interessant søk.

Kilde for data: [Stortinget](https://data.norge.no/nlod/no) - under [Norsk lisens for offentlige data (NLOD) 2.0](https://data.norge.no/nlod/no/2.0)

Start med å velge `stortings-periode` og indekser. Dette skal laste ned data fra data.stortinget.no via noen APIer, transformere og indeksere dem. Så skal du kunne søke i disse dataene.

Trenger en søkeinformasjons-modell som viser partier, representanter og saker og metadataene + APIene som er tenkt brukt og vist.

## Søkeinformasjons-modell

![Tegning av søkeinformasjons-modell](https://github.com/eklem/stortinget-dataset-search/blob/trunk/search-information-model-v01.png)

Foreslåtte entiteter å kunne søke etter:

* Politiske partier
* Representanter
* Saker

## API-innhold

Ser så langt ut som interessante data. Litt vanskelig å skjønne hvordan voteringer-APIene fungere og hvordan aggregere dette. Særlig for saker som blir enstemmig vedtatt.

### Stortingsperioder og sesjoner

https://data.stortinget.no/eksport/stortingsperioder?format=json
https://data.stortinget.no/eksport/sesjoner?format=json

### Saker

https://data.stortinget.no/eksport/saker?sesjonid=2022-2023&format=json

### Sak

https://data.stortinget.no/eksport/sak?sakid=94625&format=json

Kobling mellom `sak` og `votering_id`:

https://data.stortinget.no/eksport/voteringer?sakid=94625&format=json

Så du kan se hva en representant stemte:

https://data.stortinget.no/eksport/voteringsresultat?voteringid=21349&format=json

### Representanter

https://data.stortinget.no/eksport/representanter?stortingsperiodeid=2021-2025&format=json

### Partier

https://data.stortinget.no/eksport/allepartier?format=json
