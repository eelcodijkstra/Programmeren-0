Een object in JavaScript is een samengestelde waarde. Een object bestaat uit een verzameling *properties* (eigenschappen). Een property heeft een naam en een waarde.

Property `p` van object `obj` noteer je als `obj.p` (lees obj z'n p). Deze notatie gebruik je zowel voor het toekennen van een nieuwe waarde aan de property, als voor het gebruik van de waarde van de property in een expressie. Voorbeelden:

```js
pos.x = 100;
console.log(pos.x);
```

Een object-waarde (*object literal*) noteer je als een opsomming van de (naam: waarde)-paren tussen accolades. Voorbeelden:

```js
var pos = {x: 0, y: 0};
var turtle = {name: "Stoffel", dir: 90, down: true};
```

In een object kun je properties met verschillende soorten waarden combineren. De waarde van een property kan ook een samengestelde waarde zijn: een object, een array, of een functie. Voorbeelden:

```js
var turtle = {dir: 90, pos: {x: 0, y: 0}};
turtle.forward = function (n) { ... };
console.log(Math.sin(x));
```

Je kunt door middel van een toekenning een nieuwe property aan een bestaand object toevoegen.

```js
turtle.color = "green";
```

> In andere talen liggen de properties (fields e.d.) van een object vaak vast bij de definitie of declaratie van het object, en kun je later geen properties meer toevoegen.

Door middel van de opdracht `delete obj.p` kun je property `p` verwijderen uit object `obj`.

## Waarvoor gebruik je objecten?

Bij de constructie van niet-triviale programma's spelen objecten vaak een belangrijke rol. *Object oriented programming* is een verzameling technieken en patronen gebaseerd op het gebruik van objecten. Sommige talen zijn speciaal hiervoor ontworpen (bijvoorbeeld Smalltalk en Java). Objecten vormen hierin het centrale thema. In een taal als JavaScript kun je veel van deze OOP technieken gebruiken.

> JavaScript zou je kunnen beschrijven als "object based": objecten zijn wel belangrijk, maar niet alles is een object, en de OOP-aanpak is niet de enige mogelijke. Je kunt in JavaScript ook patronen van *functioneel programmeren* gebruiken.

Je kunt objecten ook gebruiken voor het modelleren van het probleemdomein: Object Oriented Modeling. Onder andere in de wereld van de computergames is dit een handige aanpak: de meeste game-**objecten** zijn dan objecten.

In latere modules zullen we aan beide aspecten aandacht besteden.

Je kunt objecten gebruiken:

* om waarden samen te stellen (groepering);
* om structuur in de namen in het programma aan te brengen (name spaces);
* als abstractiemechanisme
    * voor het definiëren van je eigen type, in de vorm van een *Abstract Data Type*;
* als constructiemethode voor samengestelde datastructuren, zoals bomen, lijsten, grafen en netwerken.

### Namen in programma's

In een niet-triviaal programma heb je te maken met heel veel namen (identifiers). Je hebt niet alleen te maken met de namen die je zelf definieert, maar ook met de namen van in de programmadelen (libraries, modules) die je van anderen gebruikt. Omdat je graag wilt werken met betekenisvolle namen, is er een groot risico op *naamconflicten*. Dit risico kun je verkleinen door objecten te gebruiken voor het groeperen van namen.

Een voorbeeld hiervan is `Math`: alle wiskundige constanten (`Math.PI`) en functies (`Math.sin`) zijn als property van het `Math`-object gedefinieerd.

In nieuwere versies van JavaScript worden globale variabelen en functies steeds meer gedefinieerd als onderdeel van een object (bijvoorbeeld: `Number.xxx` voor `xxx`.)

Er zijn nog meer technieken om in JavaScript handig met namen om te gaan. Deze komen in latere modules aan bod. (REF???)

### Object: toestand en operaties

Je kunt in een object zowel waarden definiëren, als functies die deze waarden gebruiken en mogelijk aanpassen. Deze waarden vormen dan samen de *toestand* van het object, en de functies de operaties op het object.

Voorbeeld: een turtle-object, met als toestand onder andere de positie, de richting, en de toestand van de pen; en met als operaties forward, right, down en up.

```js
var turtle = {dir: 0, pos: {x: 0, y:0}, down: true};

turtle.forward = function(n) {...};
turtle.right = function(n) {...}

turtle.forward(10);
turtle.right(45);

```
In een latere les behandelen we hoe je een dergelijk object met functies kunt definiëren.



### Object: Abstract Data Type

In het voorbeeld hierboven kun je de toestand van de turtle direct inspecteren, via `turtle.pos`, bijvoorbeeld. Je kunt deze toestand ook veranderen - bijvoorbeeld `turtle.pos.x = 100;`. Maar in veel gevallen wil je een dergelijke directe verandering niet toestaan - bijvoorbeeld omdat het tot een inconsistente toestand kan leiden.

Je kunt een object ook zo definiëren dat je alleen het precies gedefinieerde interface vrijgeeft voor gebruik. De implementatie van het object scherm je dan af. Dit geldt in het bijzonder voor de waarden die samen de toestand vormen: deze kunnen dan alleen via het interface veranderd worden, niet als property van het object.

We geven hier een voorbeeld zonder veel uitleg. In een andere les beschrijven we hoe dit werkt, en hoe je dit gebruikt.

```js
function makeCounter () {
  var val = 0;
  
  function up() { val = val + 1; }
  function down() { val = val - 1; }
  function reset() { val = 0; }
  function value() { return val; }
  
  return {reset: reset, up: up, down: down, value: value};
}

var countA = makeCounter();

countA.inc();
console.log(countA.value());

```

Na deze definitie kun je een tel-object aanmaken met: 

Je kunt hierop alleen de operaties `x.up()`, `x.reset()`, `x.value()`, en `x.down()` uitvoeren.

### Object als parameterlijst 

Functies met twee of hooguit drie parameters zijn nog goed te hanteren. Maar als het aantal parameters groter wordt, dan wordt het al lastig om te onthouden wat wat is. Dit is nog lastiger als sommige parameters optioneel zijn.

Een manier om dit probleem op te lossen is om een object als parameterlijst te gebruiken. Voorbeeld:

```js
function moveTo (newPos) {...}

moveTo({x: 100, y: 200, penDown: true, color: green});

```

## Referenties (verwijzingen)

Een variabele die als waarde een object heeft, bevat een *verwijzing* (reference) naar dat object, niet het object zelf. Voor eenvoudig gebruik maakt dat niet zoveel uit, maar bij de volgende gevallen moet je opletten:

* kopiëren van objecten (toekenning, parameteroverdracht);
* vergelijken van objecten (test op gelijkheid);
* meerdere variabelen die naar eenzelfde object verwijzen.

### Aliasing

Bij een toekenning van een object aan een variabele, krijgt deze variabele een verwijzing naar het object. Er wordt geen kopie van het object gemaakt.

Het resultaat kan zijn dat er meerdere variabelen naar hetzelfde object verwijzen. Dit noemen we ook wel *aliasing*.

```js
var posA = {x: 10, y: 20};
van posB = posA;
```

We hebben nu de situatie als in FIG X. Als we het object via `posB` veranderen, zien we het resultaat via `posA`, en omgekeerd:

```js
posB.y = 30;
console.log(posA.y); // ==> 30
```

Op deze manier kunnen verschillende variabelen, parameter, en properties naar hetzelfde object verwijzen.


### Cyclische objecten

We kunnen met behulp van deze verwijzingen ook cyclische objecten maken: objecten die naar zichzelf verwijzen. Een elementair voorbeeld:

```js
var cycle = {val: 0; next: null};
cycle.next = cycle;

cyle.next.next.next.next = 10;
console.log(cycle.next);  // ==> 10
```
> Hint: maak een tekening van deze situatie.

### Kopiëren van een object

Zoals we hierboven gezien hebben, betekent de toekenning van een object-waarde het maken van een nieuwe verwijzing naar het object. Hoe kun je toch een kopie van een object maken?

Als het object niet te ingewikkeld is, dan kun je hiervoor een omweg nemen via een string, bijvoorbeeld in JSON:

```js
var posB = JSON.parse(JSON.stringify(posA));
```

Dit werkt voor eenvoudige objecten, maar in de volgende situaties moet je extra maatregelen treffen:

* als een object interne verwijzingen bevat, dan worden deze niet overgenomen: als een deel-object driemaal voorkomt, dan worden daar drie onafhankelijke kopieën van gemaakt;
* JSON kan niet omgaan met cykels in objecten: je moet in dat geval zelf een oplossing verzinnen waarbij de cykel eerst verwijderd wordt voordat je deze via JSON in een string omzet;
* JSON kan niet omgaan met JavaScript `Date` waarden: deze worden wel netjes in een string omgezet, maar bij de `parse` wordt er geen `Date`-waarde van gemaakt.

(Oplossingen voor deze problemen?)


### Vergelijken van object-waarden

Voor het vergelijken van object-waarden, in `objA === objB` gebruikt Javascript een vergelijking van de referenties: als beide variabelen naar hetzelfde object verwijzen, zijn ze gelijk, anders niet. Je kunt dit ook zien als een vergelijking op de *identiteit* van objecten, in plaats van op de waarde.

Met op dat `objA === {p: 10}` altijd in `false` resulteert.

Als je de waarden van de properties van de objecten wilt vergelijken, dan moet je daarvoor een eigen functie maken.




## Vragen en opmerkingen

### Deep copy

Eén van de manieren om een kopie te maken van een JavaScript-object is om dit eerst in een string om te zetten, met behulp van JSON:

```js
var copyX = JSON.parse(JSON.stringify(x));
```

Deze methode kun je niet altijd gebruiken:

* voor cyclische datastructuren werkt dit niet;
* je kunt deze ook niet gebruiken als er sprake is van sharing tussen verschillende objecten;
* waarden van het type `Date` worden niet door JSON ondersteund;
    * deze worden wel in een string omgezet, maar de omzetting van string naar `Date` gebeurt niet. Je hebt daarvoor te weinig informatie (er is geen tag om een Date-waarde te onderscheiden).

### Dictionary, hash table

De properties van een object kun je ook als string-waarde gebruiken in een index-notatie. De volgende opdrachten hebben hetzelfde resultaat:

```js
pos['x'] = 100;
pos.x = 100;
```

De index-notatie `obj["p"]` heeft meer mogelijkheden dan de notatie `obj.p`:

1. de index kan het resultaat van een berekening zijn; 
2. de index kan een willekeurige string zijn - inclusief vreemde tekens, of gereserveerde woorden als `function`.

Een voorbeeld van het gebruik hiervan is als je wilt weten welke woorden in een tekst voorkomen, en hoe vaak elk woord voorkomt. Je gebruik een woord dan als index.

```js
word = getNextWord(txt);
if (word in count.keys) {
  count[word] = count[word] + 1;
} else {
  count[word] = 0;
}
```

In sommige talen wordt een dergelijke vorm een Dictionary genoemd, of een associatief array.

> Hier zit een kleine adder onder het gras: elk object, ook als je dit initialiseert met `{ }`, erft de keys van `Object`. Als je dat wilt voorkomen, maak je het object aan met: `var count = Object.create(null);` Zie [empty object](http://adripofjavascript.com/blog/drips/creating-objects-without-prototypes.html).

In nieuwere versies van JavaScript kun je een `Map` gebruiken: de index (key) kan dan een willekeurige JavaScript-waarde zijn.

## Overige

* Classificatie
    * overerving (inheritance)   
* Agents; objecten met autonomie; eigen proces.
    * (coroutines, in Simula67)
    
### Welke context?

Volgende modules:

* Games - JS voor games
* HTML - JS

### Turtle als object

* gebruik van meerdere turtles. (Heeft vooral zin in game-context.)
* 

NB:

* gebruik voor definitie; (vgl.: Math; pos)
* concreet voor abstract;
* gebruik voor programmeren leidend, niet programmeertaal;