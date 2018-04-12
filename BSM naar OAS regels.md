# Vertaling van BSM naar OAS
Dit document beschrijft een aantal regels voor het vertalen van een bericht structuur model naar Open API Specificaties 3.0.

## Subtypen
Een entiteittype die een subtype is van een ander entiteittype wordt afgeleid met allOf:

allOf:
	- $ref: '#/components/schemas/{supertype-componentnaam'
	- type: object
	  properties:
      {elementen van het subtype}

Bijvoorbeeld:
```
natuurlijkPersonen:
  type: object
  description: Een PERSOON zijnde een mens.
  properties:
    academischeTitel:
      $ref: '#/components/schemas/academischeTitel'
    omschrijvingAcademischeTitel:
      type: string
      description: De omschrijving behorende bij NEN-tabel 'Academische titelcode'.
      maxLength: 80
      example: dr
ingeschrevenNatuurlijkPersonen:
  allOf: '#/components/schemas/natuurlijkPersonen'
  type: object
  description: Een NATUURLIJK PERSOON ingeschreven in de Basisregistratie Personen (BRP).
  required:
    - burgerservicenummer
  properties:
    burgerservicenummer:
      type: integer
      description: Het burgerservicenummer, bedoeld in artikel 1.1 van de Wet algemene bepalingen burgerservicenummer.
      example: 999999138
    burgerlijkeStaat:
      type: string
      enum:
        - onbekend
        - ongehuwd en nooit gehuwd geweest
        - gehuwd
        - gescheiden
```

## Required
Onder required worden alle elementen opgenomen met [Mogelijk geen waarde] == Nee.

Bijvoorbeeld:
```
required:
  - stemmingsidentificatie
  - stemmingstype
  - eindresultaat
```

## Properties
Bij de vertaling van properties van een object zijn op een aantal plekken aannames gedaan over de vertaling. Hierbij is geprobeerd de specificaties en implementatie daarvan zo eenvoudig mogelijk te houden. De gewenste vertaling moet dan worden bepaald in een koppelvlakproject op basis van businessbehoefte en optimalisering voor implementatie.

Elk element wordt opgenomen met minimaal type, description (uit notes) en example (als die er is).

__ISSUE__: Sommige elementnamen bevatten punt, maar DSO gebruikt punt (expand, fields, sortering) voor properties in gegevensgroep, relatie, enz.
__ISSUE__: Hoe komen we aan voorbeeldwaarden (example)? Is daar al tagged value voor in MIM? Zijn er al voorbeeldwaarden opgenomen in UGM (of doen we dat altijd pas op BSM niveau)?

### Enumeratiesoort
```
type: string
enum:
	- {enumeratie waarde}
	- {volgende enumeratie waarde}
```
In parameters worden enumeratiewaarden opgenomen als [waarde1, waarde2, waarde3]

### Complex datatype
```
$ref: '#/components/schemas/{complexdatatype-componentnaam}'
```


### Gegevensgroep
```
$ref: '#/components/schemas/{gegevensgroep-componentnaam}'
```

### Tabel-entiteit
Element opnemen in \_embedded

### Interface: NEN3610ID
```
$ref: '#/components/schemas/NEN3610'
```

### Extern interface: gml
Element opnemen in \_embedded

### Union
Waarschuwing geven in Imvertor

### Relatie
Element opnemen in \_embedded

### DATUM
```
type: string
format: date
```

### DATUM?
```
type: string
format: date
nullable: true
```

### JAAR
```
type: integer
maximum: 9999
```

### JAARMAAND
```
type: integer
maximum: 999999
```

### DT
```
type: string
format: date-time
```

### DT?
```
type: string
format: date-time
nullable: true
```

### POSTCODE
```
type: string
pattern: ^[1-9]{1}[0-9]{3}[A-Z]{2}$
```


### INDIC
```
type: boolean
```

### AN, AN[x]
Formeel patroon
Minimum lengte

```
type: string
pattern: ^{Formeel patroon}$
minLength: {Minimum lengte}
maxLength: {x}
```

### N, N[n]
Minimum waarde (inclusief)
Maximum waarde (inclusief)

```
type: integer
minimum: {Minimum waarde (inclusief)}
maximum: {Maximum waarde (inclusief)}
```
__AANNAME__: We maken geen onderscheid in format int32 of int64.
__AANNAME__: Maximale lengte [n] van integer hoeft (en kan?) niet te worden afgedwongen in schema

### N[n],[d]
Minimum waarde (inclusief)
Maximum waarde (inclusief)

```
type: number
minimum: {Minimum waarde (inclusief)}
maximum: {Maximum waarde (inclusief)}
```

### TXT
```
type: string
```

### URI
```
type: string
format: uri
```
__AANNAME__: Verdere uitwerking (bijvoorbeeld pattern voor uri) is niet nodig
