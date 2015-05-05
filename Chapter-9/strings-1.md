## Strings

Een tweede soort waarde in JavaScript is de *String*: een rij tekens, bijvoorbeeld letters, cijfers, en andere tekens. Meestal gebruik je strings voor leesbare tekst.

### Waarvoor gebruik je strings?

Zowel mensen als computers kunnen goed met tekst, in de vorm van strings, omgaan. Dit betekent dat we strings vaak tegenkomen in het interface tussen mens en computer: bij invoer en uitvoer, als programmatekst, als data, en bij protocollen waar zowel mensen als computers bij betrokken zijn.

Bovendien is tekst gestandaardiseerd, in de vorm van Ascii of Unicode (UTF-8, enz.). Hierdoor is tekst heel geschikt voor de uitwisselen van gegevens tussen programma's en tussen computers. Tekst leent zich ook goed voor het bewaren van gegevens. Vormen als XML of JSON kom je daardoor overal tegen.

> Het gaat hier om platte tekst: een reeks tekens zonder verdere opmaak in de vorm van kleur, lettertypes en dergelijke.

Internet-protocollen zoals mail (POP, SMTP) en HTTP zijn ook gebaseerd op tekst. Dit maakt het gemakkelijker om deze protocollen "met de hand" uit te voeren, en om te zien wat er misgaat bij de interactie met een server.

### Notatie van string-literals

In JavaScript noteer je een letterlijke stringwaarde (*string literal*) als een reeks tekens tussen een paar quotes (aanhalingstekens). Je kunt hiervoor zowel enkele als dubbele quotes gebruiken. Enkele voorbeelden:

```js
var spatie = ' ';
var hello = 'Hello World';
var number = "1234";
var letterA = "A";
```

#### Lengte van een string; de lege string

De lengte van een string `str` krijg je door middel van: `str.length`.

Voor de voorbeeld-string `spatie` geldt: `spatie.length === 1`. Een string van lengte 1 is in JavaScript een normale string. Er is geen aparte notatie voor een enkelvoudig teken.

> Sommige andere talen maken verschil tussen een enkelvoudig teken (character) en een string van lengte 1.

De string `""` of `''` heeft lengte 0. Dit noemen we *de lege string*.

> We spreken over *de* lege string, omdat er maar één lege string is. Op dezelfde manier spreken we over *de* lege verzameling, of over *het* getal 0.


#### Bijzondere tekens in strings

Je kunt in de notatie voor een string literal alleen zichtbare tekens opnemen, uit een beperkt alfabet (tekenset). Als je speciale tekens in een string wilt opnemen, zoals de overgang op een nieuwe regel, dan gebruik je een *escape-notatie*, met het teken \ (backslash) als escape-teken:

* `"\n"` - newline, overgang op een nieuwe regel
* `"\\"` - het teken `\ ` zelf
* `"\""` - het teken `"`
* `"\'"` - het teken `'`

Voorbeelden: 

```js
str1 = "Voor een string literal gebruik je \" of \' ";
str2 = "Hello\nWorld";
```


#### Unicode-tekens

Een string bestaat in JavaScript uit Unicode-tekens. Je kunt bijzondere tekens uit verschillende talen in een string opnemen. Je gebruikt hiervoor de notatie "\uXXXX", waarin `XXXX` de hexadecimale notatie voor het Unicode-teken is.

```js
var copyrightSymbol = "\u00A9";
```

### Wat kun je met strings doen?

Er zijn in JavaScript heel veel operaties op strings beschikbaar:

* elementaire operaties: aaneenrijgen van strings (concatenatie); selecteren van tekens of deelstrings;
* vergelijken (gelijkheid; volgorde);
* omzetten van een JavaScript-waarde in een string, en omgekeerd (conversie).
* zoeken
* pattern matching (`str.match`, reguliere expressies)
* ontleden van een string (parsing)

We behandelen hier alleen de eenvoudige operaties. In latere hoofdstukken en modules komen de andere operaties aan de orde.

### Concatenatie (aaneenrijgen)

Met behulp van de operator `+` kun je twee of meer strings aaneenrijgen tot een nieuwe stringwaarde:

```js
var guest = "Mary";
var welcome = "Hi " + guest + ", welcome to our website";
var long = "This could be " +
  "a very long string";
```

We gebruiken deze operator soms ook om lange stringwaarden weer te geven, die niet op één regel in het programma passen.

> Een alternatief is om een regel in het programma te splitsen, met behulp van het teken \ aan het eind van de tekstregel. Een nadeel is dat je dan de vervolgregels niet netjes kunt laten inspringen.

```js
var long = "This is an example\
of a long line in the program text;"
```

Merk op dat in JavaScript de `+` operator meerdere betekenissen heeft: je gebruikt deze voor het optellen van getallen, en voor het aaneenrijgen van strings. Je moet dan uit de context opmaken wat er bedoeld wordt. Dit is opletten als je in een expressie zowel strings als getallen gebruikt. (Zie ook verderop, onder Conversie.)

### Selecteren (indicering)

Het eerste teken van een string heeft index (positie) 0. Door middel van `str[i]` of `str.charAt(i)` selecteer je het teken op positie `i` in string `str`.

Als de positie `i` buiten de stringwaarde `str` valt, krijg je als resultaat van `str.charAt(i)` de lege string. Indicering met `str[i]` levert de lege waarde (`null`).

Je kunt ook een deelstring selecteren. Je geeft de beginpositie op en de lengte (`substr`) of de eindpositie (`slice`).

* `str.slice(beginSlice[, endSlice])`
* `str.substr(start[, length])`

De positie `endSlice` is de eerste positie *na* de deelstring.
Een negatieve index bij `slice` telt vanaf het eind van de string; `-1` is de positie van het laatste teken. (Een negatieve index `i` komt overeen met index `length + i`.)

> Je kunt op deze manier alleen een teken of een deelstring (substring) opvragen. Een string is een onveranderlijke waarde ("immutable"): je kunt een string niet veranderen door middel van indicering. (In andere talen kan dat soms wel.)


### Omzetten van een waarde in een string (conversie)

Je kunt een enkelvoudige waarde `x` (getal, boolean, `null`) in een string omzetten door middel van `x.toString()`.

Voor samengestelde waarden werkt deze methode maar zeer beperkt. In dat geval kun je de waarde beter omzetten met behulp van JSON (zie verderop).

#### Van getal (Number) naar string

Als je een getal gebruikt op een plek waar een string verwacht wordt, dan wordt dit getal omgezet naar een string. Dit komt vooral voor bij het aaneenrijgen van strings, met de `+` operator. Omdat deze ook voor optellen gebruikt wordt, moet je hierbij goed opletten.

Wat is de handigste aanpak om problemen te voorkomen? (Wat zeg Crockford hierover?)

| Expressie &nbsp; &nbsp; &nbsp; &nbsp; | Resultaat |
| :---          |  ---:     |
| `123 + 4`     | `127`     |
| `4 + 123`     | `127`     |
| `"123" + "4"` | `"1234"`  |
| `"123" + 4`   | `"1234"`  |
| `4 + "123"`   | `"4123"`  |


### Zoeken (en vervangen)



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
