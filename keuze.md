Keuze (IF)

In dit hoofdstuk maak je kennis met de IF-constructie. Deze gebruik je als de actie die uitgevoerd moet niet altijd dezelfde is. Afhankelijk van de \*conditie\* wordt de ene of de andere opdracht uitgevoerd. De notatie hiervoor in JavaScript is:

```js
if (condition) {
  actionA;
} else {
  actionB;
}
```

Als de `condition` de waarde `true` \("waar"\) oplevert, dan wordt `action1` uitgevoerd; als de `condition` `false` \("onwaar"\) is, wordt `actionB` uitgevoerd.

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

_Opdracht:_ definieer een functie `abs` voor het bepalen van de _absolute waarde_ van een getal. \(De absolute waarde $$|x|\$$ van een getal $$x$$ is $$x$$, als $$x >= 0$$; anders is dit $$-x$$. De absolute waarde van 4 is 4; de absolute waarde van -3 is 3.\)

### Hoe gebruik je de keuze-constructie?

In welke gevallen gebruik je deze keuze-constructie? Waar moet je dan op letten?

* verschillende gevallen - verschillende acties;
* grensgevallen;
* partiële operaties

### Grensgevallen

#### Partiële operaties

Sommige opdrachten zijn alleen maar mogelijk als de parameters aan een bepaalde conditie voldoen. Zo is deling `a / b` alleen gedefinieerd als `b` niet 0 is \(`b !== 0`\). En de wortel $$\sqrt{x}$$ is alleen gedefinieerd voor $$x \geq 0$$.

_Opdracht_ geef nog een voorbeeld van een partiële operatie, uit de wiskunde, of uit een programmeertaal.

Als je een functie definieert, heeft deze soms voor bepaalde waarden geen betekenis. Of je moet er zelf een betekenis voor verzinnen.

Voorbeelden:

* wat betekent \`forward\(-3\)? Kun je hier een zinvolle betekenis aan geven?
* wat betekent `right(-90)`? Kun je hier een zinvolle betekenis aan geven?
* wat betekent `vierkant(-100)` - voor het tekenen van een vierkant van grootte `-100`?

In de definitie van zo'n functie zul je deze speciale gevallen vaak onderscheiden van het normale geval met behulp van een keuze-opdracht.

