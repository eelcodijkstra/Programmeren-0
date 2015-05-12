Een array is een rij soortgelijke elementen. Het rangnummer van een element in een array noemen we de *index*. Het eerste element in de rij heeft index 0.

> In de Informatica is het gebruik om te tellen vanaf 0. Dit geldt ook voor de index in een array. Dit vereenvoudigt het gebruik, en verkleint daarmee de kans op fouten. We zullen later voorbeelden hiervan zien.

In JavaScript kun je een array beschouwen als een rij variabelen; elke variabele kun je afzonderlijk een waarde geven.

We kunnen een array-waarde noteren door de elementen op te sommen, tussen vierkante haken :`[ ]`.

```js
var primes = [2, 3, 5, 7, 11, 13, 17, 19, 23];
var names = ["Hans", "Jannie", "Henk", "Ingrid", "Marlies"];

```

Je kunt een enkel element in een array aanduiden door middel van de index, tussen vierkante haken, bijvoorbeeld `primes[3]`.

Voor bovenstaande arrays geldt: `primes[0] === 2` en `names[3] === "Ingrid"`.

Een index is een expressie: deze kan dynamisch zijn, dat wil zeggen uitgerekend worden tijdens de uitvoering van een programma. Je komt dan vormen tegen als `primes[i * 2]`, of `names[f(x)]`.

### Arrays voor de constructie van programma's

Een array is een samengesteld datatype - net als een object. Je kunt arrays zien als één van de manieren om waarden samen te stellen.

Arrays en herhaling horen bij elkaar.

In JavaScript heb je een aantal vormen van herhaling ingebouwd in de taal (of in de library):

* `a.forEach(f)` - voer de functie `f` uit voor alle elementen van het array `a`.
* `a.map(f)` - bereken een nieuwe array-waarde, uit het toepassen van `f` op elk element van `a`
* `a.reduce(f)` - bereken een waarde door `f` toe te passen *tussen* alle elementen van `a`

We zullen van elk van deze functies voorbeelden geven.

We gebruiken een array vaak voor het opslaan van een reeks soortgelijke gegevens. Soms kunnen we de index gebruiken om een gegeven direct terug te vinden. Soms moeten we zoeken: in dat geval kan het handig zijn om het array gesorteerd te houden, zodat we gebruik kunnen maken van *Binair Zoeken*.


#### Andere voorbeelden van het gebruik van arrays

* als bouwsteen voor andere datastructuren: queue, stack, tape, verzameling, bag;
* als model van het geheugen;
* buffering - bijvoorbeeld FIFO (queue) of LIFO (stack)
* uitwisselen van ruimte tegen tijd: je kunt een array ook zien als een (discrete) functie, soms is het handiger om de functiewaarden op te slaan, dan om de functie steeds uit te rekenen. Dit geldt zeker als je de functie steeds voor dezelfde argumenten moet uitrekenen. (Caching; dynamisch programmeren)

### Hoe gebruik je arrays bij het oplossen van problemen?

Sommige problemen hebben een structuur die direct samenhangt met een array:

* tabellen (vgl. ook spreadsheets; databases);
* vectoren en matrices;

Een tabel bestaat gewoonlijk uit een aantal rijen (regels), waarbij elke rij dezelfde indeling heeft. Een enkele rij kunnen we dan voorstellen als een object, met een veld (property) voor elke kolom.

> Denk bijvoorbeeld aan een kasboek: elke regel komt overeen met een transactie. Per transactie heb je bijvoorbeeld een volgnummer, datum, omschrijving, tegenrekening, en bedrag.

We kunnen een dergelijke tabel in een programma beschrijven (modelleren) als een array van objecten: voor elke rij een object.

Het optellen van de waarden in de kolom `bedrag` kunnen we dan bijvoorbeeld als volgt doen:

```js
function sum (x, y) {
  return x + y.bedrag;
}

totaal = kasboek.reduce(sum, 0);

```

Ook in het geval van databases gebruiken we vaak tabellen - in het bijzonder voor relationele databases.


> NB: in de functie `sum` is `x` de accumulerende variabele. Zie de definitie van `reduce`. De initiële waarde hiervoor is 0: de tweede parameter van reduce.

We kunnen dit ook schrijven als:

```js
var totaal = 0;

function addItem(x) {
  totaal = totaal + x.bedrag;
}

kasboek.forEach(addItem);
```

Dit is denk ik in dit geval niet eens veel minder duidelijk. (Je moet het principe van deze optelling wel eens gezien hebben.)

```js
var totaal = 0;
var i;

for (i = 0; i < kasboek.length; i = i + 1) {
  totaal = totaal + kasboek[i].bedrag;
}
```

In verkorte notatie:

```js
var totaal = 0;
kasboek.forEach(function (x) {
  totaal = totaal + x.bedrag;
});
```
