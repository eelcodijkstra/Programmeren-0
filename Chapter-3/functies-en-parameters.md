# Functies en parameters

Het programma uit het vorige voorbeeld is in meerdere opzichten primitief. We zullen zien hoe we met een eenvoudige uitbreiding al veel verder komen.

In dit hoofdstuk introduceren we het Javascript `function` - concept.

Een functie of procedure is een stukje script (handelingsvoorschrift) dat we een naam geven. We kunnen dit script dan op allerlei verschillende plaatsen gebruiken. We hoeven dan bij dit gebruik niet steeds de opdrachten daarin te herhalen: we kunnen volstaan met het *aanroepen* van die functie of procedure. In Javascript heet dat een *function call*.

We kennen dit ook van scripts (algoritmen) uit het dagelijks leven:

* in een recept kan een deelrecept gebruikt worden, bijvoorbeeld voor *sauce hollandaise*. Elke kok weet aan de hand van de naam wat er bedoeld wordt, en heeft hier geen verdere toelichting nodig. Een beginnende kok kan eventueel de uitleg van het deelrecept elders vinden.

Het is belangrijk om bij functies de verschillende begrippen goed uit elkaar te houden:

* de *definitie* van de functie: we beschrijven de functie, en koppelen een functie-naam aan een reeks opdrachten;
    * dit kun je vergelijken met een deelrecept in een kookboek: je beschrijft de ingrediënten en de opdrachten van het deelrecept, en geeft dit een naam.
* de *aanroep* van een functie: in Javascript, de naam van de functie, gevolgd door een haakjespaar met de parameters - bijvoorbeeld: `forward(10)`:
    * een aanroep is een opdracht;
    * het gebruik van een deelrecept als opdracht in een ander recept, bijvoorbeeld voor sauce hollandaise.
* deze aanroep geeft aanleiding tot het een *proces*: het *uitvoeren* van de functie, dat wil zeggen: het uitvoeren van de reeks opdrachten uit de functie-definitie;
    * het bereiden van de sauce hollandaise;
* het *resultaat* van een functie-aanroep;
    * de saus - in het geval van het deelrecept voor sauce hollandaise.

We zullen deze begrippen nog enkele malen in voorbeelden toelichten.

| Beschrijving | Opdracht | Proces    | Resultaat    |
| ---       | ---      | ---       | ---       |
| deelrecept  | gebruik als opdracht | koken | saus |
| functie-definitie | functie-aanroep  | uitvoering (executie) | resultaat |

## Functie-aanroep

In JavaScript bestaat de aanroep van een functie uit de naam van de functie gevolgd door een paar haakjes met daartussen een lijst van parameters:

```
 functienaam(...parameters...)
```
De lijst parameters kan leeg zijn, dan krijg je alleen de haakjes: `()`.

Elementaire opdrachten voor de turtle zoals `penDown()` en `forward(20)` zijn  voorbeelden van functie-aanroepen - met 0 en 1 parameter(s), in dit geval.

## Functie-definitie

Een volgende stap is dat we zelf een functie definiëren. De vorm hiervan in JavaScript is:

```js
function naam(...parameters...) {
  ... opdrachten ...;
}
```
Enkele voorbeelden van functie-definities zonder parameters:

```js
function zijde100() {
  forward(100);
  right(90);
}
```
en

```js
function vierkant100() {
  zijde100();
  zijde100();
  zijde100();
  zijde100();
}
```

Bij het gebruik (aanroep) van een functie hoeven we alleen te weten wat het effect (resultaat) van deze functie is. We hoeven niet te weten uit welke opdrachten deze functie bestaat.

> Programmeurs houden er niet van om zichzelf te herhalen (DRY: don't repeat yourself). In dit voorbeeld wordt de opdracht `zijde()` vier maal herhaald. In de volgende les zullen we zien hoe we dat slimmer kunnen doen.

## Parameters

De voorbeelden die we hierboven gezien hebben kunnen maar één ding. Deze functies hebben altijd hetzelfde effect. We kunnen functies algemener bruikbaar maken door deze te voorzien van *parameters*. In de genoemde voorbeelden ligt het voor de hand om de lengte van de zijde als parameter te gebruiken:

```js
function zijde(length) {
  forward(length);
  right(90);
}

function vierkant(size) {
  zijde(size);
  zijde(size);
  zijde(size);
  zijde(size);
}
```

Met de functie `vierkant` kunnen we zo vierkanten tekenen van een willekeurige grootte. Deze is algemener bruikbaar dan de eerdere functie `vierkant100`.

De functie `zijde` kunnen we eigelijk alleen gebruiken voor het tekenen van een vierkant, of een deel daarvan. De vaste hoek van 90 graden, in `right(90)`, zorgt ervoor dat deze functie beperkt bruikbaar is.

We kunnen deze functie algemener bruikbaar maken door ook de hoek als parameter mee te geven. We krijgen dan:

```js
function zijde(length, angle) {
  forward(length);
  right(angle);
}

Met deze functie kunnen we een vierkant tekenen:

function vierkant(size) {
  zijde(size, 90);
  zijde(size, 90);
  zijde(size, 90);
  zijde(size, 90);
}
```

Met de laatste versie van `zijde` kunnen we ook andere veelhoeken tekenen dan alleen vierkanten.

```js
function driehoek(size) {
  zijde(size, 120);
  zijde(size, 120);
  zijde(size, 120);
}
```

## Samenstellingen

We kunnen nu ook eenvoudig samengestelde figuren maken. We kunnen de eerder genoemde functies als bouwsteen gebruiken, en daar weer andere figuren mee maken.

### Voorbeeld: huis

We kunnen door de driehoek en het vierkant te combineren, een eenvoudig huisje tekenen:

```js
function huis(size) {
  right(-60);
  driehoek(size);
  right(60);
  vierkant(size);
}
```

Een aanroep van deze functie, bijvoorbeeld `huis(50);`, heeft als resultaat:

> ![Figuur van een huis](figs/house50.png)

### Voorbeeld: straat

```js
function huisStap(size) {
  huis(size);
  forward(size);
}
```

```js
function straat(size) {
  huisStap(size);
  huisStap(size);
  huisStap(size);
}
```

Een aanroep `straat(30);` geeft als resultaat:

> ![Figuur van een straat](figs/street.png)

Je kunt de functie `huisStap` ook koppelen aan een knop (button). Je herhaalt de functie-aanroep dan door een aantal malen op deze knop te klikken.
