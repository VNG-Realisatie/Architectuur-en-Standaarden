# Use cases
1. Ik wil een document toevoegen
	* In GitHub onder tab "Code" klik op "Create new file"
	* Vul de bestandsnaam. Vergeet niet de extensie. Voor een tekstdocument met opmaak (mark down) is dat .md
	* Vul de inhoud van het document
	* Vul bij "Propose new file" een korte titel voor de bijdrage en een uitgebreide toelichting
	* Klik op "Propose new file"

2. Ik wil een (tekst)document wijzigen
	* Op en het document vanuit tab "Code" door te klikken op de bestandsnaam
	* Klik op het pen-icoon
	* Voor de toevoegingen of wijzigingen door in de inhoud van het document
	* Vul bij "Propose new file" een korte titel voor de toevoegingen of wijzigingen en een uitgebreide toelichting hiervan
	* Klik op "Propose file change"

3. Ik wil een opmerking maken over een bijdrage van iemand anders
	* Ga naar de bijdrage vanuit tab "Pull requests" door op de titel van de bijdrage (≠ titel van document) te klikken
	* Vul onderaan de pagina bij "Write" het commentaar
	* Klik op de knop "Comment"

4. Ik wil reageren op een opmerking van iemand anders op een pull request
	* Ga naar de bijdrage vanuit tab "Pull requests" door op de titel van de bijdrage (≠ titel van document) te klikken
	* Klik op het invulveld (Reply…) onder de betreffende opmerking
	* Vul bij "Write" je reactie op de opmerking
	* Klik op de knop "Add a single comment" (wat is het verschil met "Start a review"?)

5. Ik wil een opmerking maken over een specifieke wijziging (gewijzigd deel van het document)
	* Ga naar de bijdrage vanuit tab "Pull requests" door op de titel van de bijdrage (≠ titel van document) te klikken
	* Ga naar tab "Files changed" (en selecteer zo nodig het gewijzigd bestand?)
	* Wijs met de muis over de betreffende gewijzigde regel (groen of rood gemarkeerd) tot er een blauw icoon met wit + erin links van de regel verschijnt. Klik op het + icoon
	* Vul bij "Write" je reactie op de opmerking
	* Klik op de knop "Add a single comment" (wat is het verschil met "Start a review"?)

6. Ik wel een correctie doorgeven (doen?) op een bijdrage (pull request) van iemand anders
	* Ga naar de bijdrage vanuit tab "Pull requests" door op de titel van de bijdrage (≠ titel van document) te klikken
	* Ga naar tab "Files changed" (en selecteer zo nodig het gewijzigd bestand?)

7. Ik wil een correctie doen op een bijdrage (pull request) van mijzelf
	* Ga naar de bijdrage vanuit tab "Pull request" door op de titel van de bijdrage (≠ titel van document) te klikken
	* Ga naar tab "Files changed" (en selecteer zo nodig het gewijzigd bestand?)
	* Klik op het pen-icoon
	* Voor de toevoegingen of wijzigingen door in de inhoud van het document
	* Vul bij "Commit changes" een korte titel voor de correctie en een uitgebreide toelichting hiervan
	* Klik op "Commit changes"

8. Ik wil een pull request intrekken

9. Ik wil anderen uitnodigen mijn bijdrage te beoordelen
	* Kan nu alleen met write access. Volgens https://help.github.com/articles/requesting-a-pull-request-review/ moet iedereen dit kunnen

10. Ik wil een bijdrage van een ander beoordelen dat deze (wat mij betreft) is goedgekeurd
11. Ik wil een bijdrage van een ander beoordelen dat er gewenste aanpassingen zijn

12. Ik wil een document in mark down schrijven
	* Zie https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf voor opmaakcodes.

# Vanuit eigen laptop/tooling
Soms wil je met je eigen editor documenten (dat kan ook code of schema zijn) bewerken. Bijvoorbeeld in XmlSpy, Eclipse, enz. Dan is het handiger om de bestanden van de repository op je eigen laptop te hebben staan en van daaruit te bewerken. Hieronder staat hoe je git kan gebruiken op je eigen laptop.

1. Ik wil een lokale werkplek beginnen van een repository
	* Preconditie: je hebt git (dat is iets anders dan GitHub!) geïnstalleerd op je computer
	* Preconditie: Om documenten te kunnen bewerken of toevoegen via een push request, moet je eerst een "fork" hebben gemaakt van de VNG Realisatie repository waar je in wilt werken.
	* Preconditie: 	Om vanuit je lokale laptop te mogen pushen naar een VNG Realisatie repository, moet je een personal access token maken. Dit access token moet als "scope" hebben "repo".
	Wanneer bij een git commando gevraagd wordt om inlognaam en wachtwoord, vul je niet je wachtwoord in, maar je personal access token.
	* Open command prompt (Windows) of Terminal (Mac)
	* Ga naar de map waarin de repository moet komen, bijv. met:
  `cd /user/vngr/github`
	* Zoek in GitHub de url van de repository die je wilt gebruiken. Onder tab "Clone" klik op de knop "Clone or download". Selecteer en kopieer de getoonde url. (In het voorbeeld hieronder wordt de repository Architectuur-en-Standaarden gebruikt)
	(vervang in de code hieronder "username" door je eigen GitHub username en "Architectuur-en-Standaarden" door de naam van de repository waar je in wilt wijzigen en "voornaam.achternaam@vng.nl" door je eigen e-mailadres)

	```git init
	git clone https://github.com/username/Architectuur-en-Standaarden.git
	cd Architectuur-en-Standaarden
	git config --global user.name "username"
	git config --global user.email voornaam.achternaam@vng.nl
	git commit --amend --reset-author```

2. Ik wil een document toevoegen
	* Voor je iets gaat wijzigen of toevoegen zorg je dat je de meest actuele toestand van de repository locaal hebt:
	`git pull`
	* Maak een branch voor de wijziging (wanneer je niet kan of wil werken op een branch die je al eerder gemaakt hebt):
	`git branch branchnaam`
	(waar "branchnaam" moet worden vervangen door een naam van je branch)
	* Zorg dat je wijzigingen betrekking hebben op deze branch:
	`git checkout branchnaam`
	(gebruik de branchnaam die je in de vorige stap hebt gemaakt)
	* Maak het document in de tool of app van jouw keuze (Notepad, Eclipse, XmlSpy, Atom, …)
	* Bekijk (optioneel) welke documenten gewijzigd zijn:
	`git status`
	* Voeg het document toe aan je staging:
	`git add bestandnaam.ext`
	(waar bestandnaam.ext moet worden vervangen door de naam (inc. extensie) van het bestand dat je hebt toegevoegd)
	* Wanneer je meerdere documenten hebt toegevoegd of gewijzigd, kan je ze ook allemaal tegelijk toevoegen aan staging met:
	`git add *`
	* Je legt de wijzigingen vast in je lokale master branch met:
	`git commit -m 'toelichting op de commit'`
	(waarbij je "toelichting op de commit" vervangt door een omschrijving van wat je hebt toegevoegd of gewijzigd)
	* Om het document naar GitHub te sturen als push request doe je:
	`git push -u origin branchnaam`
	(waar "branchnaam" moet worden vervangen door de naam van de branch die je bij bullit 2 hebt gemaakt)
	* Om een pull request te maken ga je naar GitHub.com, en daar naar je eigen account en daarin de betreffende repository. Bijvoorbeeld https://github.com/username/Architectuur-en-Standaarden
	* Selecteer de branch die je hierboven (bij bullit 2) hebt gemaakt.
	* Klik "New pull request". Vul een titel en omschrijving van de pull request die beschrijft wat je waarom hebt gewijzigd of toegevoegd.
3. Ik wil een document wijzigen
4. Ik wil een correctie doen op een bijdrage van iemand anders
