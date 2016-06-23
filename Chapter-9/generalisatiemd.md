# Generalisatie

Bij het programmeren speelt *generalisatie* een belangrijke rol. Vaak maken we de stap van een bepaald probleem naar een algemener probleem. Eén van de manieren daarvoor is het vervangen van een constante door een parameter.

Voorbeelden:

* van `function square40()` naar `function square(size)`
* van `function square(size)` naar `function polygon(n, size)`

Bij het vervangen van een constante door een parameter moet je het algoritme in de body van de functie generaliseren. Dit betekent dat je op zoek moet naar een algemener patroon. In het geval van het polygon betekent dit dat je de relatie tussen de grootte van de hoek en het aantal zijden begrijpen:

```js
function polygon(n, size) {

  function edge() {
    forward(size);
    right(360 / n);
  }
  
  repeat(n, edge);
}
```

In dit geval is het product tussen de draaiing (parameter van `right`) en het aantal zijden (`n`) gelijk aan 360 graden: een complete draai.

## Generalisatie bij herhaling

Bij het oplossen van een probleem met herhaling zoek je naar het algemene patroon van een stap. Daarbij kan het helpen om de eerste paar stappen eerst als concreet probleem op te lossen. Vervolgens probeer je die oplossingen dan te generaliseren.


