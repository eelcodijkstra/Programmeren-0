# Rekenen met getallen

In de voorbeelden hiervoor hebben we steeds gewerkt met "letterlijke" getallen (*literals*): een reeks cijfers in de programmatekst.

In dit hoofdstuk gaan we rekenen met getallen.

In JavaScript zijn er ook andere waarden dan getallen, bijvoorbeeld strings (tekenreeksen), booleans (logische waarden), en samengestelde waarden in de vorm van objecten en arrays. Deze waarden komen in latere hoofdstukken aan bod.

> In de meeste voorbeelden gebruiken we gehele getallen. In JavaScript kan een getal ook een drijvende-komma getal zijn. In veel andere talen maak je uitdrukkelijk verschil tussen gehele getallen en drijvende-komma getallen; in JavaScript maak je dat onderscheid niet.

Een expressie (rekenkundige uitdrukking) in JavaScript bestaat uit waarden - in de vorm van letterlijke getallen, parameters, functie-aanroepen - en operatoren - zoals `+`, `-`, `*`. en `/`. In een expressie van de vorm `a + b` noemen we `a` en `b` ook wel de operanden van de operator `+`.

Enkele voorbeelden van expressies:

```js
2 + 3 * 4
(2 + 3) * 4
Math.sqrt(4) + 12
(-b + Math.sqrt(b * b - 4 * a * c)) / (2 * a)
```

Een expressie kun je zien als een rekenvoorschrift: je geeft aan hoe het resultaat uitgerekend moet worden, uit de waarden die in de expressie gebruikt worden, met behulp van de operatoren.

> Een verschil met expressies in de gebruikelijke wiskundige notatie is dat je vermenigvuldiging altijd moet schrijven als `*`, bijvoorbeeld `2 * a`. Je kunt dit niet afkorten als `2a`.

## Operatoren

## Functies met resultaat

De functies die we eerder behandeld hebben, geven een *effect*, bijvoorbeeld in de vorm van een tekening op het scherm. Hieronder behandelen we "echte" functies, die een waarde opleveren als resultaat. Door middel van de opdracht `return expr;`, waarbij `expr` één of andere expressie is, geef je het functieresultaat aan.

Voorbeeld:

```js
function dubbel(x) {
  return x * 2;
}
```

Een aanroep van deze functie, bijvoorbeeld `dubbel(10)`, levert een getal op. Overal waar een getal verwacht wordt, kunnen we een dergelijke functie-aanroep schrijven. Gebruik bijvoorbeeld het volgende voorbeeld in het console:

```js
dubbel(20) + 50
```

We kunnen met de bouwstenen die we hebben willekeurig ingewikkelde expressies schrijven:

```js
dubbel(dubbel(10) + 5)) * 2
```

> *Opmerking*: we schrijven hier geen `;` na de aanroep van een functie; dat is omdat het niet op een opdracht (statement) gaat, maar om een waarde. Deze waarde willen we mogelijk met andere waarden in een expressie combineren. Ook na een getal schrijven we geen `;`.


Zoals je in dit voorbeeld ziet, kan een parameter ook een getal voorstellen, en kunnen we overal waar in een expressie een getal verwacht wordt, een parameter gebruiken.

## Parameters

Zoals we al in eerdere voorbeelden gezien hebben, kan een parameter ook een getal voorstellen. Waar in een expressie een getal verwacht wordt, kunnen we ook een parameter schrijven. Voorbeelden:

```js
function driehoek(omtrek) {
  driehoekszijde(omtrek / 3);
  driehoekszijde(omtrek / 3);
  driehoekszijde(omtrek / 3);
  }
```

