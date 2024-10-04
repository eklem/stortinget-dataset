# stortinget-dataset
Dataset from data.stortinget.no to create an interesting offline search.

Start selecting `stortings-periode` and index it. This will download data from data.stortinget.no through a few APIs and index it. Then you are ready to search that data.

Need a search information model showing documents, data and metadata to connect the different entities.

## Search information model



## API Content

So far, what looks like interesting data. Also need how the representatives vote and be able to aggregate that to political parties. The two first is to get which sessions to fetch and index:

### Stortingsperioder and sesjoner

https://data.stortinget.no/eksport/stortingsperioder?format=json
https://data.stortinget.no/eksport/sesjoner?format=json

### Saker

https://data.stortinget.no/eksport/saker?sesjonid=2022-2023&format=json

### Sak

https://data.stortinget.no/eksport/sak?sakid=94625&format=json

Connection between `sak` and `votering_id`:

https://data.stortinget.no/eksport/voteringer?sakid=94625&format=json

So you can see what a person voted:

https://data.stortinget.no/eksport/voteringsresultat?voteringid=21349&format=json

### Representanter

https://data.stortinget.no/eksport/representanter?stortingsperiodeid=2021-2025&format=json

### Partier

https://data.stortinget.no/eksport/allepartier?format=json
