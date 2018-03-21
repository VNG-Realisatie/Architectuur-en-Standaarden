# Criteria voor een koppelvlakstandaard
Voor het beoordelen van een standaard kunnen we kijken vanuit verschillende perspectieven:
* Vanuit de doelstellingen voor het maken van koppelvlakstandaarden
* Criteria voor een open standaard (Forum standaardisatie)
* Eigenschappen van een goede standaard (SIG)
* Beheersmatige en bestuurlijke familiecriteria
* Inhoudelijke familiecriteria
* Niet functionele eisen aan een koppelvlakstandaard

## Doelstellingen van koppelvlakstandaardisatie
* **Interoperabiliteit**: (door een eenduidig service contract); Interoperabiliteit maakt het mogelijk om op basis van een interfacedefinitie “standaard stekkers en stopcontacten” te maken die altijd passen. Hierdoor kunnen koppelingen worden hergebruikt, loont voorinvestering in koppelingen en is minder maatwerk nodig voor het bouwen van koppelingen. Compliancy met andere (internationale) standaarden speelt hierbij een belangrijke rol
* **Kostenreductie**: Naast minder maatwerk voor het bouwen van koppelingen en hergebruik van bestaande code door interoperabiliteit moet de standaard eenvoudig met behulp van (recente versies van) de gangbare ontwikkelomgevingen te implementeren zijn. Daarnaast moet het StUF instrumentarium voor authenticatie en autorisatie aansluiten op hetgeen door de gangbare IAM voorzieningen en voorzieningen voor API management (WS gateway’s, servicebussen e.d.) wordt ondersteund. De bovengenoemde voordelen leiden tot kostenreductie tijdens bouw en operatie
* **Bevorderen marktwerking**: Marktwerking zal worden bevorderd wanneer de standaard dusdanig is opgezet (laagdrempelig & niet complex) dat voorinvestering (in stekkers/stopcontacten) loont, en de investering voor nieuwkomers relatief laag is. Een hoge adoptiegraad (veel stekkers om te bedienen, veel stopcontacten om op aan te sluiten) heeft een aanzuigende werking. Ook de aansluiting bij moderne architectuurstijlen speelt een rol bij adoptie van de standaard door nieuwe jonge spelers in de markt
* **Bevorderen innovatie**: Innovatie wordt bevorderd door adoptie binnen de standaard van gangbare architectuurstijlen en formaten voor gegevensuitwisseling met moderne consumers. Denk aan mobile devices, the internet of things (IoTs), en Linked Data. Hierbij is het belangrijk om te constateren of het wijzigingsproces met name gericht is op “aanjagen en bijblijven” of op “backward compatibility” t.b.v. bestaande systemen?

## Criteria voor een open standaard volgens Forum standaardisatie
Het Forum Standaardisatie noemt de volgende criteria voor een open standaard:
* De benodigde documentatie moet laagdrempelig beschikbaar zijn.
* Er mogen geen hindernissen zijn op het terrein van intellectueel eigendomsrecht.
* Er moeten voldoende inspraakmogelijkheden zijn voor stakeholders tijdens de (door)ontwikkeling van de standaard.
* De onafhankelijkheid en duurzaamheid van de standaardisatieorganisatie moeten verzekerd zijn.

## Eigenschappen van een goede standaard (SIG)
In het rapport "Analyse van de StUF- BG standaard" d.d. 25 september 2015, opgesteld door de Software Improvement Group in opdracht van de Gemeente Den Haag worden een aantal eigenschappen benoemd waar een goede standaard aan moet voldoen:
* **Geaccepteerd**: Door een autoriteit en/of een groep belanghebbenden
* **Gangbaar**: Het gebruik wordt algemeen als normaal beschouwd
* **Toepasselijk**: Toepasbaar binnen een afgebakend domein of probleem set
* **Bruikbaar**: Wordt ervaren als eenvoudig in gebruik. Vermindert de inspanning/drempel om de standaard te gebruiken.
* **Volwassen**: Voldoende ondersteunende tooling, ervaring, documentatie. Referentie implementatie(s)
* **Stabiel**: Gestructureerd verbeteringsproces, wijzigingen zijn backward compatibel

## Beheersmatige en bestuurlijke beoordelingscriteria
In het StUF beheermodel wordt een aantal beheersmatige en bestuurlijke beoordelingscriteria genoemd, waar de Regiegroep Gegevens- en Berichtenstandaarden een (kandidaat) nieuwe koppelvlakstandaard op moet toetsen:
* R01. Beheercontinuiteit >= 3 jaar
* R02. Duidelijkheid afhankelijkheid met andere StUF onderdelen (bijv. een configuratieplaatje)
* R03. Release beleid incl. releasefrequentie en aansluitend op afhankelijke familieleden
* R04. Heldere besluitvorming- en participatiestructuur
* R05. Vaste vertegenwoordiger beheerorganisatie in regiegroep
* R06. Specificaties publiekelijk toegankelijk
* R07. Beschreven beheermodel op basis van StUF beheermodel
* R08. Inzicht in (voorgenomen) implementaties

## Inhoudelijke beoordelingscriteria
In het StUF beheermodel wordt een aantal inhoudelijke beoordelingscriteria genoemd, waar de (StUF) Expertgroep een (kandidaat) nieuwe koppelvlakstandaard op moet toetsen:
* E01. Duidelijkheid over de plek in de familiestructuur 
* E02. Duidelijkheid organisatorisch en functioneel werkingsgebied
* E03. Voldoet aan de regels van de StUF onderlaag (o.a. validerende schema’s)
* E04. Voldoet aan de StUF specificatie voor protocolbindingen
* E05. Een structuurplaatje waarin de opbouw van de schema’s wordt duidelijk gemaakt (documentatieverplichting)
* E06. Contactgegevens beheerder van berichtcatalogus
* E07. Voldoet aan naamgeving- en versienummering conventies en andere eisen (namespace conventies) die aan een sectormodel worden gesteld (zie best practices document: comply or explain)
* E08. Optimaal hergebruik bestaande StUF-onderdelen
* E09. Geen conflicten met andere StUF-onderdelen
* E10. Relatie en transformatie tussen nieuwe en voorgaande versies van sectormodellen en berichtcatalogi.

## Niet functionele eisen aan een koppelvlakstandaard
In de koppelvlakspecificaties voor RSGB bevragingen 1.0 wordt een aantal niet functionele eisen genoemd voor een koppelvlakstandaard:
* **Bruikbaarheid**
  * Platform onafhankelijk
  * Object georiënteerde schema's
  * Referentie implementatie
* **Ondubbelzinnigheid**
  * Definieer het standaard koppelvlak zo expliciet mogelijk 
* **Zelfdocumenterend**
  * Standaard koppelvlakdefinitie zoveel mogelijk zelfbeschrijvend
  * Gebruik "tot en met" in plaats van "tot" 
* **Codegeneratie**
  * Gegenereerde code zoveel mogelijk zonder aanpassingen bruikbaar
* **Consistentie**
  * Pas Camelcasing consequent toe
  * Gebruik enkelvoud of meervoud om de berichtnaam expliciet en passend te maken. Gebruik voor de elementen altijd enkelvoud. 
  * Pas vormgeving en terminologie consistent toe binnen de hele koppelvlakstandaard en binnen de familie van koppelvlakstandaarden 
* **Formaten**
  * Ondersteun naast een XML SOAP interface ook andere formaten en architectuurstijlen
  * Houd de REST API zoveel mogelijk gelijk aan de SOAP Service API
* Het **serialiseren** van en naar XML of JSON wordt ondersteund door de meeste gangbare ontwikkelomgevingen
  * Lever testprojecten op waarmee aantoonbaar is voldaan aan de eis dat consumers en providers van verschillende platformen met elkaar kunnen communiceren 
  * Lever testprojecten op waarmee is aangetoond dat de gegenereerde code zonder aanpassingen bruikbaar is. 
