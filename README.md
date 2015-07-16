# Postcode API 2.0
Deze repository bevat het API design (op basis van [Swagger](http://swagger.io)) voor de nieuw te bouwen versie van de [Postcode API](http://www.postcodeapi.nu). Via deze repository kan er gediscussieerd worden over gewenste features en de structuur van de API. Voel je vrij om de spec te forken en via Pull Requests eventuele verbeteringen en wijzigingen aan te dragen. De meest actuele leesbare spec [hier te vinden](https://htmlpreview.github.io/?https://raw.githubusercontent.com/apiwise/postcodeapi/master/docs/index.html). Admins van deze repository zijn @joostfarla en @dvh.

## Wat gaat er veranderen?
Postcode API 2.0 wordt volledig van scratch ontwikkeld met de nieuwste technologieën. Hierdoor zal de nieuwe versie een enorme performance boost krijgen. Tevens streven wij naar een RESTful architectuur, waardoor adressen en postcodes los van elkaar te benaderen zijn. Een *adres* is immers iets anders dan een *postcode* + *huisnummer* combinatie. Door de scheiding is er nu ondersteuning voor meerdere straten binnen één postcode, huisnummer toevoegingen en letters. Ook bevat de API *hypermedia* links om eenvoudig door de data heen te kunnen navigeren. De brondata wordt opgeschoond en vaker en accurater ververst. De gebruikte identifiers blijven gelijk aan die van de brondata waardoor er eenvoudig met andere (overheids) datasets is te koppelen.

## TODO
- Linked Data support via JSON-LD
- Verrijking van geometrie
- Koppelen van andere datasets
- Postbussen toevoegen (als iemand deze kan vinden horen wij het graag ;-))

## Credits
Postcode API 2.0 wordt ontwikkeld en onderhouden door [Apiwise](http://www.apiwise.nl) en is een vervolg op het oorsponkelijke idee van [Freshheads](http://www.freshheads.com). Neem contact met ons op via [Twitter](https://twitter.com/apiwise) of [e-mail](info@apiwise.nl).
