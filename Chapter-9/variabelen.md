
## Variabelen: namen en hun betekenis; toestand

## Toestand van de turtle

De toestand van de turtle bestaat uit zijn positie in het vlak, zijn richting, en de toestand van de pen (op het papier, of niet). Deze geven we in het programma weer door middel van de *variabelen* `pos.x`, `pos.y`, `dir` en `down`. Deze variabelen beschrijven samen de toestand van de turtle.

> Je hebt aan deze toestand voldoende om te weten wat de betekenis van opdrachten in de toekomst is. Je hoeft daarvoor niet de hele geschiedenis te weten: de toestand kun je zien als het netto resultaat van deze geschiedenis.

Door het uitvoeren van de opdrachten als `forward(10)` of `penDown()` verandert de toestand van de turtle. Dit zien we terug in de *waarden* van deze variabelen.

> De toestand van een proces wordt beschreven door de waarden van alle variabelen van dat proces.

### Een stukje van het proces

We kunnen een stukje van een proces van de turtle weergeven, als veranderingen in de toestand. We laten hierbij even het eigenlijke resultaat: de lijnen op het papier of op het scherm, even buiten beschouwing.

Links staan de opdrachten die uitgevoerd wordten, rechts daarvan de waarden van de variabelen *op dat punt in het proces*.

| opdracht       | `pos.x` | `pos.y` | `dir` | `down` |
| :---           | :---    | :---    | :---  | :---   |
| ...            | `100`   | `50`    | `90`  | `True` |
| `forward(20);` | `100`   | `70`    | `90`  | `True` |
| `right(90);`   | `100`   | `70`    | `180` | `True` |
| `forward(20);` | `80`    | `70`    | `180` | `True` |


### Andere voorbeelden

Het *saldo* van je bankrekening is een voorbeeld van een variabele die een toestand beschrijft. Het is het netto-resultaat van alle transacties in het verleden. Voor de betekenis van de transacties in de toekomst is alleen dit saldo van belang.

## Variabelen

### Declaratie

We introduceren een nieuwe variabele in een programma door middel van een *declaratie*. Deze bestaat uit de volgende onderdelen:

* een indicatie dat we een nieuwe variabele (naam) introduceren; in JavaScript gebruiken we daarvoor het *reserved word* `var`.
* de naam van de variabelen.
    * voor de computer moet deze naam uniek zijn (binnen een bepaalde context);
    * voor de programmeur moet deze naam *betekenisvol* zijn. Aan de naam moet je kunnen aflezen wat de rol van deze variabele is in het programma.
* meestal een *initiële waarde*.
* soms (in commentaar) een verdere uitleg van de betekenis.

Enkele voorbeelden:

```js
var n = 0;
var som = 0; // som van kwadraten van 0..n-1

```

Enkele opmerkingen hierbij:

* we kunnen in JavaScript meerdere variabelen tegelijk invoeren. We gebruiken dan een komma als scheidingsteken. Voor het voorbeeld hierboven wordt dit dan:

```js
var 
  n = 0,
  som = 0; // som van kwadraten van 0..n-1
```
Volgens sommige stijlregels moet je alle variabele-declaraties in een functie op deze manier combineren. (JSLint)

> In sommige talen moet je ook nog aangeven welk soort waarden een variabele aan kan nemen: je geeft het type van de variabele aan. In JavaScript is dat niet nodig, omdat het type onderdeel is van de waarde - en niet van de variabele. Een JavaScript-variabele kan waarden van verschillende types aannemen.

### Gebruik

### Toekenning

```js
som = som + n * n;
n = n + 1;

```

* de volgorde van deze toekenningen is van belang.
* in Python kun je ook schrijven:

```python
som, n = som + n * n, n + 1
```

### Een stukje van een proces

| opdracht             | `n    ` | `som  ` | 
| :---                 | :---    | :---    |
| ...                  | `5`     | `14`    |
| `som = som + n * n;` | `5`     | `29`    |
| `n = n + 1;`         | `6`     | `29`    |

### Idem

| opdracht             | `n    ` | `som  ` | `P(som, n)` |
| :---                 | :---    | :---    |             |
| ...                  | `5`     | `14`    | `som = SOM(i<n: n^2)`       |
| `som = som + n * n;` | `5`     | `29`    | `som = SOM(i<n: n^2) + n^2` |
|                      | `5`     | `29`    | `som = SOM(i<n+1: n^2)`     |
| `n = n + 1;`         | `6`     | `29`    | `som = SOM(i<n: n^2)`       |

### Namen en waarden

* in de meeste programmeertalen kun je een naam invoeren en koppelen aan een tussenresultaat, zodat je dit resultaat op andere plekken kunt gebruiken.
* soms verandert de koppeling tussen de naam en het tussenresultaat niet, in de loop van het programma ("proces"). We spreken dan over een constante. In sommige talen heb je hiervoor een aparte taalconstrutie.
* in andere gevallen wil je de naam ook weer aan een nieuw tussenresultaat kunnen koppelen. We spreken dan over een *variabele*.
    * de koppeling van een naam aan een waarde gebeurt door middel van een zogenaamde *toekenning* (assignment).
    
door middel van een variabele kun je een naam geven aan een tussenresultaat, zodat je dit op andere plekken kunt gebruiken. 
* 
* bij een "echte variabele" kun je de koppeling tussen de naam en de waarde veranderen, door middel van een toekenning (assignment).

### Namen en betekenis (en waarde)

Een variabele (of constante, parameter) heeft in een programma een bepaalde *betekenis*. Dit kun je ook zien als de rol die deze variabele speelt.

Soms bestaat deze betekenis uit de relatie tussen meerdere variabelen. (Vgl. invariant)

* kies betekenisvolle namen. 

### Een model van het geheugen

Je kunt variabelen ook zien als een model van het werkgeheugen van de computer.

* je geeft een naam aan een geheugencel die een bepaalde waarde kan bevatten.
* door middel van een toekenning verander je de waarde in die geheugencel.


Een object kun je zien als de groepering van een reeks variabelen: dit komt overeen met een stuk van het geheugen, ofwel een reeks geheugencellen.

In het geval van functies of procedures 

"Laatjes" of "hokjes".


### Scope: welke definitie hoort bij welk gebruik (voorkomen) van een naam?

Als we een naam (identifier) tegenkomen op een bepaalde plaats in een programma, moeten we de definitie van deze naam kunnen vinden - en daarmee de betekenis.

> Eenzelfde naam kan op verschillende plaatsen in een programma gedefinieerd zijn. Als we een naam invoeren met een bepaalde betekenis , dan willen we niet verplicht worden om een nieuwe, unieke naam te bedenken: een groot programma kan vele duizenden namen bevatten, de administratie daarvan De namen in een programma Als de namen in een programma allemaal uniek zouden zijn, 
kunnen vinden waar deze naam gedefinieerd is. 
Hoe vind je bij het gebruik van een naam in een programma de bijbehorende definitie, waar die naam ingevoerd wordt?

Hoe vind je bij het gebruik van een variabele in een programma de bijbehorende koppeling aan een waarde?

* Eigenlijk wil je dit niet weten: op elk punt in het programma moet de naam gekoppeld zijn met een waarde die klopt met de betekenis. Deze betekenis beschrijf je bij de invoering van de naam. Vaak is de naam zelf 

## Gebruik voor het bouwen van programma's

* soms gebruiken we een variabele om een naam te geven aan een waarde; deze koppeling verandert dan niet meer (eigenlijk is hier sprake van een geïnitialiseerde constante).
* een variabele heeft vooral zin in combinatie met keuze of met herhaling

## Gebruik voor het oplossen van problemen


> Namen in wiskundige vergelijkingen hebben een andere rol dan namen in programma's. In een vergelijking staat een naam voor een *onbekende*. Door de vergelijking op te lossen, kun je de mogelijke waarde(n) voor die onbekende vinden. Hierbij is het $=$-teken volledig symmetrisch: je kunt links en rechts verwisselen zonder dat de betekenis (van gelijkheid) verandert.

> In de Wiskunde gebruiken we meestal namen als *x* en *y*, of *i* en *j*. het belangrijkste is dat we namen van elkaar kunnen onderscheiden. De betekenis van een naam doet niet ter zake.


## Enkele opmerkingen over terminologie

* we moeten onderscheid maken tussen "variabele" en "naam" (identifier, spelling). Een *variabele is een naam met een betekenis*. Deze betekenis wordt gegeven door de declaratie (voor de machine) en door de beschrijving (voor de mens, in de context van het programma). Een naam komt overeen met een betekenis: we moeten dan de declaratie van die naam vinden. De scope-regels bepalen welke betekenis bij een bepaalde naam hoort.

(In JavaScript heb je eigenlijk maar één soort naam, afgezien van de voorgedefinieerde namen. In principe zijn alle namen variabele-namen. Ook een functienaam kun je herdefiniëren...)


## Werkt het ook omgekeerd?

Kun je door direct de variabelen van de turtle te veranderen, de toestand van het systeem veranderen?

* in het geval van de turtle werkt dit wel; dit is omdat deze variabele de toestand vormen (een representatie zijn van?). 
* in veel andere gevallen is dit niet zo, omdat de variabelen dan de toestand weergeven, maar niet vormen. (Hoe noem je dit? Een model van de eigenlijke toestand?)
* in het geval van het banksaldo werkt dit niet, in elk geval niet op langere termijn: het saldo is de samenvatting van een reeks van transacties, en het is altijd weer te herleiden uit deze transacties (die bewaard blijven). Een verandering van het saldo zonder bijbehorende transactie is verdacht.

In het geval van de turtle:

* voor een virtuele turtle, bijvoorbeeld voor het tekenen op het Canvas, is het mogelijk om door toekenning aan de positie-variabelen de positie van de turtle aan te passen. Dit is een vorm van "teleportatie".
    * het is de vraag of je dit wilt - dat hangt af van de context. Je kunt de toegang tot de variabelen eventueel afschermen, als je dat wilt. (=> Information hiding)
* voor een fysieke turtle, bijvoorbeeld een robot die tekenend over het papier beweegt, is een verandering van de positie alleen nodig door opdrachten als `forward` en `right`. 