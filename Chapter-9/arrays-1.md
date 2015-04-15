Een array is een rij soortgelijke elementen. Het rangnummber van een element in een array noemen we de index. Het eerste element in de rij heeft index 0.

> In de Informatica is het gebruik om bij tellen te beginnen bij 0. Dit geldt ook voor de index in een array. Dit vereenvoudigt het gebruik, en verkleint daarmee de kans op fouten. We zullen later voorbeelden hiervan zien.

In JavasScript kun je een array beschouwen als een rij variabelen; elke variabele kun je afzonderlijk een waarde geven.

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


### Hoe gebruik je arrays bij het oplossen van problemen?

Sommige problemen hebben een structuur die direct samenhangt met een array:

* tabellen (vgl. ook spreadsheets);
* vectoren en matrices;

