Keuze \(IF\)

In dit hoofdstuk maak je kennis met de IF-constructie. Deze gebruik je als de actie die uitgevoerd moet niet altijd dezelfde is. Afhankelijk van de uitkomst van de \*conditie\* wordt de ene of de andere opdracht uitgevoerd. De syntax hiervoor in JavaScript is:

```js
if (condition) {
  actionA;
} else {
  actionB;
}
```

Als de `condition` "waar" is, dat wil zeggen, de waarde `true` oplevert, dan wordt `action1` uitgevoerd. Als deze `condition` "onwaar" is, ofwel `false`, wordt `actionB` uitgevoerd.

### Vergelijken van waarden

De conditie bevat vaak een vergelijking tussen twee waarden. Voor alle waarden kunnen we testen op gelijkheid:

| vergelijking | betekenis |
| :---         | :---      |
| `a === b`    | `a` is gelijk aan `b` |
| `a !== b`    | `a` verschilt van `b` |

Voor getallen hebben we meer mogelijkheden:

| vergelijking | betekenis |
| :---         | :---      |
| `a > b`      | `a` is groter dan `b` |
| `a >= b`     | `a` is tenminste `b`  |
| `a < b`      | `a` is kleiner dan `b` |
| `a >= b`     | `a` is ten hoogste `b` |


Enkele voorbeelden

### maximum

We definiëren een functie voor het 

```js
function max

