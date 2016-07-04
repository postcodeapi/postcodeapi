# Postcode API
Deze repository bevat het API design (op basis van [Swagger](http://swagger.io)) voor versie 2 van de [Postcode API](http://www.postcodeapi.nu). Via deze repository kan er gediscussieerd worden over gewenste features en de structuur van de API. Voel je vrij om de spec te forken en via Pull Requests eventuele verbeteringen en wijzigingen aan te dragen. De meest actuele API documentatie [is hier te vinden](https://swaggerhub.com/api/apiwise/postcode-api). Admins van deze repository zijn [@joostfarla](https://github.com/joostfarla) en [@dvh](https://github.com/dvh).

## Wat zijn de grootste veranderingen t.o.v. Postcode API 1.0?
De nieuwe API is volledig gebouwd op de cloud infrastructuur van Amazon Web Services en heeft daardoor een zeer snelle response tijd en hoge uptime. Hierdoor is de API uiterst geschikt en zeer betrouwbaar voor bedrijfskritische applicaties. Ook is de documentatie geüpdatet, zorgt de nieuwe response structuur ervoor dat de API naadloos integreert met populaire frameworks en via Swaggerhub kunnen verschillende client libraries en code voorbeelden gedownload worden. De kwaliteit van de data is sterk verbeterd door o.a. de toevoeging van NEN-5825 notatie voor adressen, GeoJSON coördinaten en de koppeling met de meest actuele brondata van de overheid.

Daarnaast is het abonnementenmodel gewijzigd. De gratis variant kent in de nieuwe versie een harde limiet van 500 calls per dag zodat wij deze gratis dienst tegen dezelfde betrouwbare kwaliteit kunnen blijven aanbieden. De twee betaalde abonnementen, Basis en Premium, kennen naast respectievelijk 2.500 en 10.000 calls per dag ook andere voordelen ten opzichte van de gratis variant. Het overzicht vind je op [onze website] (http://www.postcodeapi.nu/#pakketten). Voldoen de pakketten niet aan jouw specifieke wensen of eisen of wil je de API inzetten voor meerdere applicaties? Schroom dan niet om contact met ons op te nemen over eventuele maatwerk oplossingen. Wij denken graag met je mee!

## Implementaties
Er zijn voor diverse talen en platforms door de GitHub community implementaties op deze api gemaakt.
* PHP: <https://github.com/freshheads/FHPostcodeAPIClient>
* PHP (Laravel): <https://github.com/nickurt/laravel-postcodeapi>
* C#/.NET: <https://github.com/BAPostma/PostcodeAPI.Net>
* Python: <https://github.com/steffex/pyPostcode>
* Ruby: <https://github.com/ariejan/postcodeapi>
* PowerShell: <https://github.com/suneetnangia/postcodeapi>

## Credits
De nieuwe Postcode API wordt ontwikkeld en onderhouden door [Apiwise](http://www.apiwise.nl) en is een vervolg op het oorspronkelijke idee van [Freshheads](http://www.freshheads.com). Neem contact met ons op via [Twitter](https://twitter.com/apiwise) of [e-mail](mailto:info@apiwise.nl).
