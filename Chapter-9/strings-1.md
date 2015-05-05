## Strings

Een tweede soort waarde in JavaScript is de *String*: een rij tekens: letters, cijfers, en andere tekens. Meestal gebruik je strings voor leesbare tekst.

### Waarvoor gebruik je strings?

Zowel mensen als computers kunnen goed met tekst, in de vorm van strings, omgaan. Dit betekent dat we strings vaak tegenkomen in het interface tussen mens en computer: bij invoer en uitvoer, als programmatekst, als data, en bij protocollen waar zowel mensen als computers bij betrokken zijn.

Bovendien is tekst gestandaardiseerd, als Ascii of Unicode (UTF-8, enz.). Hierdoor is tekst een geschikte vorm  voor het uitwisselen van gegevens tussen programma's en tussen computers. Tekst leent zich ook goed voor het bewaren van gegevens. Vormen als XML of JSON kom je daardoor overal tegen.

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

De lege string is de *nul-waarde* voor concatenatie; voor elke string `str` geldt:

* `str + "" === str`
* `"" + str === str`

> Dit heet de nul-waarde: voor optellen met het getal 0 gelden vergelijkbare regels.

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
var long = "This is an example \
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

> Je kunt op deze manier alleen een teken of een deelstring (substring) opvragen. Je kunt de stringwaarde niet veranderen: een string is in JavaScript een onveranderlijke waarde ("immutable"). In andere talen kun je stringwaarde soms wel veranderen.


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

Soms willen we meer invloed hebben op de precieze notatie van het getal, bijvoorbeeld het aantal posities na de decimale punt. Hiervoor kunnen we de volgende functies gebruiken:

* `num.toFixed(n)` - `n` cijfers na de decimale punt
* `num.toExponential(n)` - exponent-notatie, `n` cijfers na de decimale punt
* `num.toPrecision(n)` - in `n` cijfers nauwkeurig

Deze operaties ronden het getal eventueel af.

#### Van string naar getal

Voor het omzetten van een `numStr` naar het bijbehorende (gehele) getal gebruiken we `parseInt(numStr, 10)`. We gebruiken hier het grondtal 10 - maar je kunt ook een een ander grondtal gebruiken.

> Het is verstandig om altijd het grondtal aan te geven. Soms wordt als default-grondtal 8 gebruikt: je krijgt dan misschien een andere uitkomst dan je gedacht had. `parseInt("0177")` levert bij sommige JavaScript-implementaties 127 op (via grondtal 8).

Voor het omzetten van een floating-point waarde gebruik je `parseFloat(x)`.

### Vergelijken

We kunnen twee strings vergelijken, om te zien of deze gelijk zijn: `str === "Hello"` of `str !== "Hello"`.

We kunnen strings ook alfabetisch vergelijken, bijvoorbeeld `str <= "Marie"`. Dit kan bijvoorbeeld handig zijn voor het zoeken naar een string, of voor het sorteren van strings.

> Voor het vergelijken van strings moet je soms gebruik maken van de volgorde die in een bepaalde natuurlijke taal gebruikelijk is. Dit heet ook wel de "Collating sequence". Hiervoor is er een speciale vergelijkingsfunctie: `str1.localeCompare(str2, locale)`. Hierin geeft `locale` de manier van vergelijken aan. 


### Zoeken

Voor het zoeken van tekens of deelstrings in een string kun je de volgende operaties gebruiken:

* `str.indexOf(x, pos)` - zoek naar het eerste voorkomen van `x` in `str`, vanaf positie `pos`. Als `x` niet voorkomt (vanaf `pos`) is het resultaat `-1`.
* `str.lastIndexOf(x), pos` - zoek naar het laatste voorkomen van `x` in `str`, vanaf positie pos. Als `x` niet voorkomt (vanaf `pos`) is het resultaat `-1`.

`indexOf` zoek van voor naar achter, `lastIndexOf` van achter naar voor.

