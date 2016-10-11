Keuze \(IF\)

In dit hoofdstuk maak je kennis met de IF- of keuze-constructie. Deze gebruik je als de actie die uitgevoerd moet niet altijd dezelfde is. Afhankelijk van de \*conditie\* wordt de ene of de andere opdracht uitgevoerd. De notatie hiervoor in JavaScript is:

```js
if (condition) {
  actionA;
} else {
  actionB;
}
```

Als de uitdrukking `condition` de waarde `true` \("waar"\) oplevert, dan wordt `action1` uitgevoerd; als `condition` `false` \("onwaar"\) is, wordt `actionB` uitgevoerd.

### Vergelijken van waarden

De conditie bevat vaak een vergelijking tussen twee waarden. Voor alle waarden kunnen we testen op gelijkheid:

| vergelijking | betekenis |
| --- | --- |
| `a === b` | `a` is gelijk aan `b` |
| `a !== b` | `a` verschilt van `b` |

Voor getallen hebben we meer mogelijkheden:

| vergelijking | betekenis |
| --- | --- |
| `a > b` | `a` is groter dan `b` |
| `a >= b` | `a` is tenminste `b` |
| `a < b` | `a` is kleiner dan `b` |
| `a >= b` | `a` is ten hoogste `b` |

Enkele voorbeelden

In een volgend hoofdstuk gaan we dieper in op Boolean waarden en uitdrukkingen.

### maximum

We definiëren een functie voor het berekenen van het _maximum_ van twee getallen. Het functieresultaat is één van de parameters, `a` of `b`. We hebben als mogelijke acties dus `return a` en `return b`. De eerste actie voeren we uit als `a` het grootste getal is: `a > b`. In het andere geval voeren we de tweede actie uit.

```js
function max (a, b) {
  if (a > b) {
    return a;
  } else {
    return b;
  }
}
```

_Vraag:_ wat verandert er als je de conditie `a >= b` gebruikt?

_Opdracht:_ definieer een functie voor het bepalen van het minimum van twee getallen.

_Opdracht:_ definieer een functie voor het bepalen van het maximum van drie getallen.

_Opdracht:_ definieer een functie `abs` voor het bepalen van de _absolute waarde_ van een getal. \(De absolute waarde $$|x|$$ van een getal $$x$$ is $$x$$, als $$x >= 0$$; anders is dit $$-x$$. De absolute waarde van 4 is 4; de absolute waarde van -3 is 3.\)

### turtle-forward

Een voorbeeld uit de functies voor turtle-graphics:

```js
function forward(n) {
  var dx = n * cos(dir);   // change in x-dir
  var dy = n * sin(dir);   // change in y-dir
  var newpos = {x: pos.x + dx, y: pos.y + dy};

  if (down) {
    ... code to draw line to newpos ...
  } else {
    pos = newpos;  // just move to newpos
  }
}
```

Als de pen `down` is, teken dan een lijn van de huidige positie naar de nieuwe positie van de turtle; als de pen niet `down` is, verplaats dan de turtle direct naar de nieuwe positie.

### IF zonder ELSE

Soms moet een actie alleen uitgevoerd worden als een bepaalde conditie `true` is. In het andere geval moet er geen actie uitgevoerd worden. In zo'n geval laten we het else-deel weg:

```js
  if (condition) {
    actionA;
  }
```

### Hoe gebruik je de keuze-constructie?

In welke gevallen gebruik je deze keuze-constructie? Waar moet je dan op letten?

* verschillende gevallen - verschillende acties;
* grensgevallen;
* partiële operaties

#### Filters

Soms moet je een opdracht alleen uitvoeren voor waarden die aan een bepaalde voorwaarde voldoen. Voorbeeld: bepaal de som van de positieve getallen uit een rij `r`:

```js
var som = 0;
r.forEach(function (x) {
  if (x > 0) {
    som = som + x;
  }
});
```

In verkorte functie-notatie:

```js
var som = 0;
r.forEach( (x) => {if (x > 0) {som = som + x;}} );
```

(Vergelijk dit met de functie voor het optellen van alle getallen in een rij.)

#### Grensgevallen

#### Partiële operaties

Sommige opdrachten zijn alleen maar mogelijk als de parameters aan een bepaalde conditie voldoen. Zo is deling $$a / b$$ alleen gedefinieerd als $$b$$ niet 0 is \($$b \neq 0$$\). En de wortel $$\sqrt{x}$$ is alleen gedefinieerd voor $$x \geq 0$$.

_Opdracht:_ geef nog een voorbeeld van een partiële operatie, uit de wiskunde, of uit een programmeertaal.

Als je een functie definieert, heeft deze soms voor bepaalde parameterwaarden geen betekenis. Of je moet er zelf een betekenis voor verzinnen.

Voorbeelden:

* wat betekent `forward(-3)`? Kun je hier een zinvolle betekenis aan geven?
* wat betekent `right(-90)`? Kun je hier een zinvolle betekenis aan geven?
* wat betekent `vierkant(-100)` - voor het tekenen van een vierkant van grootte $$-100$$?

In de definitie van zo'n functie zul je deze speciale gevallen vaak onderscheiden van het normale geval met behulp van een keuze-opdracht.

