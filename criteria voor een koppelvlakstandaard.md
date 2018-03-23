![VNG Realisatie](https://www.vngrealisatie.nl/sites/all/themes/king/img/logo_primary_desktop.png)
# Criteria voor een koppelvlakstandaard
Voor het beoordelen van een standaard kunnen we kijken vanuit verschillende perspectieven:
* Vanuit de doelstellingen voor het maken van koppelvlakstandaarden
* Criteria voor een open standaard (Forum standaardisatie)
* Eigenschappen van een goede standaard (SIG)
* Niet functionele eisen aan een koppelvlakstandaard
* Beheersmatige en bestuurlijke familiecriteria
* Inhoudelijke familiecriteria

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

De volgende criteria zouden hieraan toegevoegd moeten worden
* Er moet ten minste één feitelijke en operationeel werkende implementatie zijn van het koppelvlak bij een gemeente.
* Specificaties en documentatie worden beschikbaar gesteld op een manier die toegankelijk is voor de relevante gebruikers (developers) en belanghebbenden van de standaard. Dit moet toegang tot de en bijdragen aan de standaard zo goed mogelijk faciliteren.
* Tijdens de ontwikkeling van (deze versie van) het koppelvlak is er voldoende ruimte geweest voor alle belanghebbenden om bij te dragen aan het koppelvlak. De bijdragen en opmerkingen van belanghebbenden zijn op de juiste manier afgewogen en meegenomen bij de ontwikkeling van de koppelvlakstandaard.

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

* Deze eisen blijven, met enige aanpassing (zie hieronder) gelden, maar controle door de StUF Expertgroep is niet voor de hand liggend, zeker niet voor API-koppelvlakken. Wellicht moeten de taken hierop verdeeld worden over verschillende expertgroepen (informatiemodellen, StUF, API, UGM). Primair moeten deze criteria onder de aandacht staan van de makers en beheerders van de koppelvlakstandaarden.
* De StUF onderlaag (**E03**) en StUF protocolbindingen (E04) gelden niet voor API's. De basisgedachte onder deze criteria blijven echter wel van toepassing: bewaken dat koppelvlakstandaarden zoveel mogelijk voldoen aan de koppelvlakoverstijgende uitwisseltechniek.
* Een structuurplaatje (**E05**) zal voor API's meestal niet relevant zijn. De Open API Specificatie dient zoveel mogelijk zelfverklarend en voldoende overzichtelijk te zijn. De documentatieverplichting op dit niveau geldt dus alleen wanneer de werking van de API niet voldoende gespecificeerd kan worden in de Open API Specificatie. Dit principe (zelfbeschrijvend specificeren is beter dan aanvullend documenteren) moet ook voor de technische definitie voor xml berichten (xsd's) gelden.
* Gebruik van de termen "berichtcatalogus" (in **E05**, **E06** en **E10**) en "sectormodel" (in **E07** en E10) moeten worden vervangen door "koppelvlakstandaard"
* Voor API's is hergebruik (**E08**) geen primair criterium. API's worden geoptimaliseerd voor eenvoud van implementatie door consumers (gebruikers) van de API, i.p.v. voor hergebruik door providers van de API.
* Het voorkomen van conflicten (**E09**) moet iets anders worden geformuleerd. Het gaat om consistentie met semantische (referentie) informatiemodel(len), uitwisselingsgegevensmodel(len). 
* Eisen van relatie en transformatie (**E10**) gelden niet of op een andere manier dan voor StUF is bedoeld. Voor API's moeten er afspraken zijn over backward compatibility (i.c.m. semantic versioning) en het ondersteunen van huidige (binnen welke tijd) en voorgaande (hoeveel versies) versies.
* Het uitwisselingsgegevensmodel (UGM)is koppelvlakoverstijgend en uitwisseltechniekoverstijgend. Het bewaken van het juiste gebruik van entiteittypen uit het UGM in koppelvlakberichten, via pas-toe-of-leg-uit, moet worden opgenomen als inhoudelijk beoordelingscriterium.
* Alle elementen in een koppelvlakbericht moeten zijn gedefinieerd in een semantisch informatiemodel.
* Bij een koppelvlakstandaard moet er een referentieimplementatie zijn voor elke API vanuit elke rol (consumer en provider, wanneer van toepassing per referentiecomponent). De code en werkende referentieimplementatie zelf zijn publiekelijk beschikbaar als onderdeel van de koppelvlakstandaard.
* De koppelvlakken (services of API's) moeten functioneel eenduidig en technisch eenduidig beschreven zijn.
* De technische specificatie van koppelvlakken (xsd's en Open API specificaties) moeten object georiënteerd zijn. Afwijken hiervan mag wanneer daar een duidelijke functionele behoefte aan ten grondslag ligt. Dit wordt bewaakt via een pas-toe-of-leg-uit principe. Deze eis geldt ook voor de entiteittypemodellering in het Uitwisselingsgegevensmodel (UGM).
* Versienummering wordt gedaan conform [Semantic versioning](https://semver.org).
* Voor operaties en berichtdefinities worden betekenisvolle namen gebruikt.
* Naamgeving van operaties en elementen (incl. relaties) is consequent en consistent met afspraken hierover in de uitwisseltechniek en namen in het betreffende UGM.

## Inhoudelijke beoordelingscriteria voor API koppelvlakstandaarden
Geïnspireerd op de beoordelingscriteria uit het StUF beheermodel met aanpassingen ten behoeve van API koppelvlakstandaarden, komen we tot de volgende beoordelingscriteria voor een koppelvlakstandaard:
* Duidelijkheid over de plek in de familiestructuur.
* Duidelijkheid organisatorisch en functioneel werkingsgebied.
* Contactgegevens beheerder van berichtcatalogus zijn bekend en gepubliceerd.
* Voldoet aan de regels van de betreffende koppelvlakoverstijgende uitwisseltechniek, dan wel er is een duidelijke business behoefte die afwijken van de koppelvlakoverstijgende uitwisseltechniek noodzakelijk maakt.
* Gegevens in berichten zijn opgenomen in dezelfde structuur als gedefinieerd in het koppelvlakoverstijgende uitwisselingsgegevensmodel (UGM), dan wel er is een duidelijke business behoefte die afwijken van het uitwisselingsgegevensmodel noodzakelijk maakt.
* Naamgeving van operaties en elementen (incl. relaties) is consequent en consistent met afspraken hierover in de uitwisseltechniek en namen in het betreffende UGM.
* Voor operaties en berichtdefinities zijn betekenisvolle namen gebruikt.
* De (technische) specificatie is zoveel mogelijk zelfverklarend. Wanneer de technische specificatie niet voldoende duidelijk en specifiek is voor de gewenste werking van de service of API, is er aanvullende documentatie beschikbaar.
* De standaard en onderdelen daarvan voldoen aan naamgeving- en versienummeringsconventies (semantic versioning) en andere eisen die aan een koppelvlakstandaard worden gesteld vanuit de koppelvlakoverstijgende uitwisseltechniek.
* Voor elk in een bericht(interacties) gebruikte entiteittype, element of relatie is verwijzing naar de semantische definitie duidelijk aangegeven naar een/het semantische (referentie) informatiemodel(len).
* Technische specificatie van de berichten (schema's) ondersteunt object georiënteerde implementatie, dan wel er is een duidelijke business behoefte die afwijken van object orientatie georiënteerde schema's noodzakelijk maakt.
* Uit de technische specificatie van de berichten (schema's) kan voor de meest gangbare platforms zonder fouten code worden gegenereerd, die zonder ingrijpende aanpassingen kan worden gebruikt. Dit is als onderdeel van de koppelvlakontwikkeling aangetoond.
* Voor elke service of API is een referentieimplementatie beschikbaar in de vorm van de programmacode (open source) en in de vorm van een werkend programma. Er is een referentieimplementatie beschikbaar voor zowel de consumer(s) van de services/API's als voor de provider(s) van de services/API's.
