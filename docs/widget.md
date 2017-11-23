# Postcode API Widget

Om de implementatie van Postcode API zo eenvoudig mogelijk te maken hebben we een client-side widget ontwikkeld.
Door middel van het plakken van een stukje HTML code in je pagina kun je binnen no-time Postcode API integreren
binnen bestaande formulieren. Er is hierbij geen server-side code benodigd!

## Requirements

Om de widget te kunnen implementeren heb je een *widget token* nodig. Om te voorkomen dat de widget door kwaadwillenden
wordt misbruikt is de widget token gekoppeld aan de *origin*. De origin is het eerste deel van het adres wat je ziet
in de adres-balk van de browser en bestaat uit het scheme (`http` of `https`), het domein (`www.voorbeeld.nl`) en
optioneel een poortnummer (`8080`).

Voorbeelden van een origin zijn:

* `https://www.voorbeeld.nl`
* `https://intranet:1234`
* `http://localhost`
* `http://localhost:8080`

Een widget token kan per mail aangevraagd worden via info@postcodeapi.nu. Stuur bij de aanvraag mee:

* De API key horende bij jouw account (heb je nog geen account, registreer dan eerst op https://www.postcodeapi.nu)
* De origin(s) waarvoor je de widget wil gebruiken
* Heb je meerdere origins (bijv in een OTAP omgeving of voor een multi-tenant implementatie), stuur dan alle verschillende origins door. Je krijgt dan een widget token per origin.

**LET OP: De widget code is niet hetzelfde als je API key!**

## Embed code

Heb je de widget token ontvangen? Voeg dan het volgende stukje code toe onderaan je HTML pagina, net voor de
afsluitende `</body>` tag. Vervang hierbij `<<PLAK HIER DE WIDGET TOKEN>>` door de ontvangen widget token.

```
<script>
  window.postcodeapi = {
    token: '<<PLAK HIER DE WIDGET TOKEN>>',
  };
</script>
<script src="https://cdn.postcodeapi.nu/widget-v1.js" async defer></script>
```

Een compleet voorbeeld zien? Kijk dan [hieronder](#voorbeeld).

## Formuliervelden

De widget verwacht standaard dat er 4 formuliervelden aanwezig zijn, die een `id` attribuut bevatten met een
bepaalde waarde. Dit zijn de standaard waardes:

| Eigenschap | `id` attribuut |
|------------|----------------|
| Postcode   | `postcode`     |
| Huisnummer | `number  `     |
| Straatnaam | `street`       |
| Woonplaats | `city`         |

Wijken de `id` attributen van jouw formuliervelden af en kun je deze niet eenvoudig aanpassen? Dan kun je
de embed code uitbreiden met de corresponderende waarden. Bijvoorbeeld:

```
<script>
  window.postcodeapi = {
    token: '<<PLAK HIER DE WIDGET TOKEN>>',
    fields: {
      postcode: 'customPostcode',
      number: 'customNumber',
      street: 'customStreet',
      city: 'customCity',
    },
  };
</script>
<script src="https://cdn.postcodeapi.nu/widget-v1.js" async defer></script>
```

## CSS classes

De widget plaatst standaard een aantal CSS classes op de formuliervelden tijdens de verwerking. Hiermee kun
je de styling van je formuliervelden aanpassen op basis van het resultaat van een Postcode API lookup.
De volgende classes worden ondersteund:

| CSS class             | Betekenis                                |
|---                    |---                                       |
| `postcodeapi-loading` | Er is een lookup bezig.                  |
| `postcodeapi-success` | De laatste lookup is succesvol afgerond. |
| `postcodeapi-error`   | De laatste lookup is mislukt.            |

## Foutafhandeling

Als er een fout optreedt, bijvoorbeeld als een postcode niet gevonden is, dan kun je de foutmelding op de pagina
laten tonen. Om dit te gebruiken dient er een leeg HTML element met class `postcodeapi-error` aanwezig te zijn.
Deze kun je op een willekeurige plek op je pagina plaatsen. Bijvoorbeeld:

```
<span id="postcodeapi-error"></span>
```

Als de postcode niet gevonden kan worden, dan worden de straat- en plaatsnaamvelden leeggemaakt. Als de lookup
om een andere reden mislukt, dan zullen de straat- en plaatsnaamvelden geleegd en geactiveerd worden, zodat
de eindgebruiker alsnog handmatig zijn adres in kan vullen. Standaard worden de velden namelijk automatisch gedeactiveerd, zodat er geen handmatige invoer mogelijk is.

## Voorbeeld

Hieronder vind je een volledig voorbeeld van een HTML pagina, gebaseerd op de Bootstrap CSS library.

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Postcode API Widget Demo</title>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap-theme.min.css" integrity="sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp" crossorigin="anonymous">
  <style>
    .postcodeapi-loading {
      border-color: orange;
    }

    .postcodeapi-error {
      border-color: red;
    }

    .postcodeapi-success {
      border-color: green;
    }

    .help-block {
      color: red;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Postcode API Widget</h1>
    <form>
      <div class="row">
        <div class="form-group col-md-8">
          <label for="postcode">Postcode</label>
          <input type="text" class="form-control" id="postcode" placeholder="Postcode">
          <span id="postcodeapi-error" class="help-block"></span>
        </div>
        <div class="form-group col-md-4">
          <label for="number">Huisnummer</label>
          <input type="text" class="form-control" id="number" placeholder="Huisnummer">
        </div>
        <div class="form-group col-md-6">
          <label for="street">Straatnaam</label>
          <input type="text" class="form-control" id="street" placeholder="Straatnaam">
        </div>
        <div class="form-group col-md-6">
          <label for="city">Plaatsnaam</label>
          <input type="text" class="form-control" id="city" placeholder="Plaatsnaam">
        </div>
      </div>
      <button type="submit" class="btn btn-default">Submit</button>
    </form>
  </div>
  <script>
    window.postcodeapi = {
      token: '<<PLAK HIER DE WIDGET TOKEN>>',
    };
  </script>
  <script src="https://cdn.postcodeapi.nu/widget-v1.js" async defer></script>
</body>
</html>
```
