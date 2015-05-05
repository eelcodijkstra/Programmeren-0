
## Hoe gebruik je strings bij de constructie van programma's?

### Tagged data

Door middel van *tags* kunnen we een tekst structuur geven, zonder de flexibiliteit va strings te verliezen.

HTML is een voorbeeld van een tagged tekst-vorm, maar je kunt hierbij alleen maar gebruik maken van een vaste verzameling voorgedefinieerde tags.

XML is een algemenere vorm hiervan: 
Een voorbeeld van een tagged data-vorm is XML; dit is een gegeneaan fleibiliteit in te boeten.


### Strings voor opslag en communicatie: JSON

JavaScript-waarden zoals getallen (Number), booleans, objecten en arrays hebben een interne representatie die je niet buiten het proces van een JavaScript-programma kunt gebruiken. String-waarden, met enkele beperkingen, zijn universeel bruikbaar, ook buiten het proces. Strings kun je daarom ook gebruiken om waarden op te slaan of te communiceren met andere computers.

###

## Hoe gebruik je strings bij het oplossen van problemen?

Veel toepassingsdomeinen gebruiken traditioneel een tekst-vorm. Denk bijvoorbeeld aan naam- en adresgegevens. De naam van een persoon is belangrijk (voor veel mensen belangrijker dan hun "nummer"). Een straat of woonplaats is ook een string.

Daarnaast is een string-representatie erg flexibel: je kunt er altijd nog elementen aan toevoegen als daar later behoefte aan is.

## PM

### JSON

Voor het opslaan van een samengestelde waarde, of voor het communiceren hiervan met een andere computer, is een string-representatie erg handig. Je bent dan niet afhankelijk van de interne representatie van bijvoorbeeld getallen. 

Speciaal voor deze doeleinden is de JSON-vorm ontwikkeld: dit is een manier om samengestelde waarden (objecten en arrays) om te zetten in een string-vorm (tekst), en omgekeerd.

* `JSON.stringify(obj)` - omzetten van `obj` in JSON-tekstvorm
* `JSON.parse(str)` - omzetten van JSON-tekstvorm (string) in JavaScript-waarde.

Enkele voorbeelden:



Let op: je kunt geen cyclische datastructuren in JSON beschrijven. Als een property verwijst naar een ander object, dan wordt dit object ook opgenomen in de JSON-representatie. In het geval van een cyclische datastructuur zou dit resulteren in een oneindig grote vorm. Gelukkig wordt bij het opstellen van een JSON-representatie hierop gecontroleerd: je krijgt een foutmelding.

Let op: je kunt geen functies in JSON beschrijven. Functies als onderdeel van een samengestelde waarde worden genegeerd.

### Gebruik van JSON

We kunnen JSON gebruiken voor het opslaan van een JavaScript-object in `localStorage`: de persistente opslag van de browser.

> *persistent* wil hier zeggen dat de waarden die in `localStorage` opgeslagen worden blijven bestaan, ook als de browser afgesloten wordt, of als de computer uitgezet wordt.


### JSON en XML

JSON kan voor dezelfde soort toepassingen gebruikt worden als XML; een voordeel van JSON is dat het minder "verbose" is: je hebt minder tekst nodig voor het beschrijven van eenzelfde object.

Bij een XML-document hoort eigenlijk ook nog een beschrijving van de structuur van dat document, in de vorm van een DTD-bestand. Voor JSON bestaat er niet een dergelijk document, om de structuur van een JSON-object te beschrijven.

Bij een REST-interface (API) van een web-dienst kun je vaak opgeven of je het resultaat in XML of in JSON wilt ontvangen.

### String als universele vorm

Strings en teksten zijn universele waarden, die voor heel veel verschillende toepassingen gebriikt kunnen worden. In principe kun je alle data en alle rekenwerk met behulp van strings doen, in plaats van met bitreeksen of getallen. Maar dit is niet altijd even efficiënt: we gebruiken daarom voor de meeste toepassingen een combinatie van verschillende soorten waarden.

### Strings, teksten en tekstverwerking

Er zijn twee manieren om teksten van bijvoorbeeld rapporten en boeken voor te stellen:

* de WYSIWG-aanpak ("What you see is what you get"), zoals gebruikt in Word en andere tekstverwerkers. In dit geval werk je met een vorm die sterk lijkt op de uiteindelijke vorm, zoals deze op papier of op het scherm eruit moet zien.
* de beschrijvende aanpak, zoals deze bijvoorbeeld voor HTML gebruikt wordt, of voor LaTeX. In dit geval werk je met een platte-tekst bestand waarin zowel de eigenlijke tekst als opdrachten voor het beschrijven van de structuur en van de opmaak staan.

### Technische termen

We gebruiken voor technische termen vaak de Engelse woorden, soms met een kleine Nederlandse aanpassing. Dit heeft als voordeel dat we een duidelijk ondescheid kunnen maken tussen technische termen met een bijzondere betekenis, en algemene termen zoals die in het Nederlands voorkomen.

* immutable (onveranderlijk) - voorbeeld: een stringwaarde is onveranderlijk.
* index (positie) - de index van letter `"W"` in `"Hello World"` is 6.

### Vragen en opmerkingen

* JavaScript heeft 3 operaties voor het selecteren van een substring: `slice`, `substr`, en `substring`. Wat zijn de subtiele verschillen? (`substring` lijkt mij eerlijk gezegd verwarrend...)

### Log