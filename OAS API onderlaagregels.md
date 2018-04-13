# Regels Open API specificatie voor gemeentelijke API koppelvlakstandaarden

## Algemeen
> Definitie van het koppelvlak is in het Nederlands tenzij er sprake is van een officieel Engelstalig begrippenkader (API-07, API-20)

## Paths
* voor een lijstopvraging: /versie/collectie
  Bijvoorbeeld: /v1/natuurlijkPersonen
* voor een enkel voorkomen: /versie/collectie/{sleutel}
  Bijvoorbeeld: /v1/natuurlijkPersonen/9991234567
* voor terugkerende queries: /versie/collectie/query
  Bijvoorbeeld: /v1/natuurlijkPersonen/minderjarigen

> "versie" begint met "v" gevolgd door alleen het major versienummer (API-24)

> "collectie" is een entiteittype (zelfstandig naamwoord) in meervoud (API-08)

__ISSUE__: Hoe vertalen we entiteittype die in UGM in enkelvoud staan (t.b.v. StUF) naar meervoud (t.b.v. API's)?

> uri-parameter "sleutel" moet voorkomen in parameters met "in: path"

  bijvoorbeeld:
  ```
  /v1/entiteiten/{entiteitid}
    (...)
    parameters:
      - in: path
        name: entiteitid
        (...)
  ```

## Operaties
> alleen standaard http operaties worden ondersteund: GET, PUT, POST, PATCH en DELETE (API-06)

## Responses
> De volgende http-statuscodes worden altijd opgenomen: 400, 409, 410, 422, 500, 503 (API-51).

__ISSUE__: Wat is het verschil (in situatie waarin je het gebruikt) tussen 409 en 422?

> De reponse op een POST ondersteunt statuscodes 201, 405, 409

__ISSUE__: Waarom is statuscode 415 niet opgenomen specifiek bij de POST, PUT en PATCH operaties (is niet relevant voor de andere operaties)

> De reponse op een GET (lijst objecten) ondersteunt statuscodes 200

> De reponse op een GET op sleutel ondersteunt statuscodes 200, 404

__ISSUE__: Waarom is statuscode 406 niet opgenomen specifiek bij de GET operaties (is niet relevant voor de andere operaties)

> De reponse op een PUT of PATCH ondersteunt statuscodes 200, 204, 404, 405, 409

> De reponse op een DELETE ondersteunt statuscodes 200, 404, 405

__ISSUE__: Waarom statuscode 200 en niet 201? Wordt er dan ooit een response body opgenomen bij een delete?

> Als caching wordt ondersteund (header Etag en/of header Last-Modified), moet resonse code 304 zijn opgenomen.

> Als belasting van de servers kan worden beperkt (headers X-Rate-Limit-Limit, X-Rate-Limit-Remaining en X-Rate-Limit-Reset zijn opgenomen), moet responsecode 429 zijn opgenomen.

> Als authenticatie relevant is voor de service, moet statuscode 401 worden opgenomen.

> ALs autorisatie van toepassing is op de service, moet statuscode 403

## Headers
> OAuth 2.0 headers zijn opgenomen, wanneer OAuth 2.0 als authenticatiemechanisme is gekozen voor de service.

> Er is een Warning header (RFC 7234) opgenomen (API-25).

> Wanneer in de responsebody geometrie is opgenomen, moet er een header "Content-Crs" zijn opgenomen (API-44).

> Wanneer er een query-parameter page is opgenomen voor de request (er kan dus worden gepagineerd), moeten de headers X-Total-Count, X-Pagination-Count, X-Pagination-Page en X-Pagination-Limit zijn opgenomen (API-46).

> Voor caching kan header Etag en/of header Last-Modified worden opgenomen.

> Belasting van de servers kan worden beperkt door headers X-Rate-Limit-Limit, X-Rate-Limit-Remaining en X-Rate-Limit-Reset op te nemen (API-49).

## Parameters
> Als er een (of meerdere) n-op-n relatie is opgenomen in de response, moet parameter expand zijn opgenomen (API-10)

> Parameters zijn elementen van het entiteittype (filters), of een van de standaard parameters expand, fields, sorteer, zoek, page.

> Parameters die verwijzen naar een element (filters) zijn gedefinieerd in camelCase (API-30).

> Een geografisch filter wordt via een POST end-point beschikbaar gemaakt (APO-40).
Dus niet als een query parameter

> Als er een path-parameter is gedefinieerd (in: path), dan moet die ook in het pad voorkomen in accolades.

## Response content (200)
> Veldnamen zijn gedefinieerd in camelCase (API-30).

> Een JSON-response heeft geen omhullende envelop (API-32).

> Verschillende contentserialisaties kunnen worden ondersteund: JSON, GeoJSON, JSON+HAL, XML, enz.

> In de JSON+HAL response content body is een element "\_links" opgenomen.
Bij alle andere contentserialisaties (zoals gewoon JSON) is "\_links" dus niet opgenomen.

> Wanneer er een query-parameter page is opgenomen voor de request (er kan dus worden gepagineerd), moeten de elementen "first", "prev", "next" en "last" in "\_links" zijn opgenomen.

> Wanneer er een query-parameter expand is opgenomen voor de request, moeten bij de relaties naast het \_links property ook de properties van de relatie of gerelateerde worden opgenomen.

__ISSUE__: Kunnen we aangeven of er historie moet worden worden opgenomen? Kan dat niet beter als element in het UGM worden toegevoegd i.p.v. ingenereren zoals voor StUF is gedaan?

### Geometrie
> Voor geometrie gebruiken we GeoJSON (API-38)

> GeoJSON is onderdeel van de embedded resource in de JSON response (API-39).

### Relaties
Wordt opgenomen in \_embedded.
Naast de properties van de relatie/gerelateerde wordt in het geval van JSON+HAL ook een \_links property opgenomen met daarin alleen property \_self (die weer de properties href en title bevat).

__ISSUE__: Hoe gaan we om met relatie-entiteiten?

__ISSUE__: Hoe gaan we ermee om als er geen relatie-entiteit is, maar wel historie op de relatie?

## Response content (400 reeks statuscodes)
> De JSON response content van een fout bestaat uit de elementen type, title, status, detail en instance.

> De JSON response content bij een POST, PUT of PATCH met statuscode 400 bestaat uit de elementen type, title, status, invalid-params.
