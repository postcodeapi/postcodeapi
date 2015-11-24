# Postcode API 2.0
Deze repository bevat het API design (op basis van [Swagger](http://swagger.io)) voor versie 2 van de [Postcode API](http://www.postcodeapi.nu). Via deze repository kan er gediscussieerd worden over gewenste features en de structuur van de API. Voel je vrij om de spec te forken en via Pull Requests eventuele verbeteringen en wijzigingen aan te dragen. De meest actuele API documentatie [is hier te vinden](http://www.postcodeapi.nu/docs/). Admins van deze repository zijn [@joostfarla](https://github.com/joostfarla) en [@dvh](https://github.com/dvh).

Versie 2.0 biedt meer functionaliteiten, betere performance en nauwkeurigere data dan zijn voorganger. Daarnaast is de nieuwe API structuur conform de laatste standaarden opgezet zodat de implementatie erg eenvoudig is en zal de data gaandeweg verrijkt worden met andere open data die relevant is voor adresgegevens. Suggesties of tips voor de geplande doorontwikkeling kunnen worden gedaan in de [Issues](https://github.com/apiwise/postcodeapi/issues) sectie.

## Wat zijn de grootste veranderingen?
De nieuwe API is volledig gebouwd op de cloud infrastructuur van Amazon Web Services en heeft daardoor een zeer snelle response tijd en hoge uptime. Hierdoor is de API uiterst geschikt en zeer betrouwbaar voor bedrijfskritische applicaties. Ook is de documentatie geüpdatet, zorgt de nieuwe response structuur ervoor dat de API naadloos integreert met populaire frameworks en via Swaggerhub kunnen verschillende client libraries en code voorbeelden gedownload worden. De kwaliteit van de data is sterk verbeterd door o.a. de toevoeging van NEN-5825 notatie voor adressen, GeoJSON coördinaten en de koppeling met de meest actuele brondata van de overheid.

Daarnaast is het abonnementenmodel gewijzigd. De gratis variant kent in de nieuwe versie een harde limiet van 500 calls per dag zodat wij deze gratis dienst tegen dezelfde betrouwbare kwaliteit kunnen blijven aanbieden. De twee betaalde abonnementen, Basis en Premium, kennen naast respectievelijk 2.500 en 10.000 calls per dag ook andere voordelen ten opzichte van de gratis variant. Het overzicht vind je op [onze website] (http://www.postcodeapi.nu/#pakketten). Voldoen de pakketten niet aan jouw specifieke wensen of eisen of wil je de API inzetten voor meerdere applicaties? Schroom dan niet om contact met ons op te nemen over eventuele maatwerk oplossingen. Wij denken graag met je mee!

## Wat betekent dit voor versie 1.0?
Huidige implementaties van de Postcode API blijven tot 1 maart 2016 gewoon werken. Daarna zal versie 1.0 uit de lucht worden gehaald en dienen alle implementaties over te zijn geschakeld naar de nieuwe versie. Hiervoor moet er wel een nieuwe API Key aangemaakt worden via [onze website](http://www.postcodeapi.nu/#pakketten).

## Roadmap
- `/postcodes` call om informatie betreffende een postcode op te vragen
- API call om gebruikersstatistieken op te vragen
- Linked Data support via JSON-LD
- Verrijking van geometrie
- Koppelen van andere datasets
- Postbussen toevoegen (als iemand deze kan vinden horen wij het graag ;-))

## Credits
Postcode API 2.0 wordt ontwikkeld en onderhouden door [Apiwise](http://www.apiwise.nl) en is een vervolg op het oorspronkelijke idee van [Freshheads](http://www.freshheads.com). Neem contact met ons op via [Twitter](https://twitter.com/apiwise) of [e-mail](mailto:info@apiwise.nl).
