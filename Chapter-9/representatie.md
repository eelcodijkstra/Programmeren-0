## Representatie 

De toestand van de turtle bestaat voor een deel uit de positie hiervan in het 2-dimensionale vlak. Meestal beschrijven we dit als een combinatie van x- en y-coördinaten, voor de turtle: `pos.x` en `pos.y`. We gebruiken hier een rechthoeking coördinatenstelsel, ook wel Cartesisch coördinatenstelsel genoemd. Maar er zijn ook andere manieren waarop we de positie van de turtle kunnen representeren - bijvoorbeeld in de vorm van poolcoördinaten. Daarnaast kunnen we nog werken met absolute coördinaten (bepaald door het vlak), of met relatieve coördinaten (ten opzichte van de turtle).

> Poolcoördinaten bestaan uit een hoek ten opzichte van (meestal) de x-as, en een lengte.

De commando's voor de turtle, zoals `forward` en `right`, zijn eigenlijk gebaseerd op *lokale poolcoördinaten*.

* de rotatie (`right`) is ten opzichte van de huidige richting van de turtle;
* de verplaatsing (lengte) is ten opzichte van de huidige positie, in de huidige richting.

Dit betekent dat we deze bewegingen om moeten rekenen in rechthoekige coördinaten.

* het commando`right(n)` kunnen we eenvoudig implementeren als `dir = dir + n;`. We hebben in dit geval geen verdere interactie met het Canvas nodig.
* het commando `forward(n)` is veel lastiger. De opdrachten van het Canvas moeten we formuleren in termen van Canvas-coördinaten: dit is een rechthoekig stelsel met linksboven het punt (0,0). De positieve x-as loopt naar rechts (zoals ook gebruikelijk in de Wiskunde). De positieve y-as loopt naar beneden (tegengesteld aan wat in de Wiskunde gebruikelijk is).

Voor het omrekenen van de verplaatsing in de richting van de turtle moeten we deze projecteren op de x-as (`dx = n * cos(dir);`) en op de y-as (`dy = n * sin(dir);`).

```js
function forward(n) {
  var dx = n * cos(dir);
  var dy = n * sin(dir);
  var newpos = {x: pos.x + dx, y: pos.y + dy};
  if (down) {
    ctx.beginPath();
    ctx.moveTo(pos.x, pos.y);
    ctx.lineTo(newpos.x, newpos.y);
    ctx.stroke();
  }
  pos = newpos;
}
```

Wat kunnen we hieruit leren?

* je kunt een toestand (model) op verschillende manieren representeren;
* je hebt meestal een grote vrijheid in de keuze van de representatie; het loont de moeite om deze vrijheid te onderzoeken;
* in het bijzonder kun je de representatie aanpassen aan de operaties die je moet uitvoeren. Afhankelijk van de gekozen representatie zijn die soms eenvoudig of complex.


## Representatie bij het construeren van programma's

Als we een programma construeren op basis van bepaalde technologie, dan kan die technologie een bepaalde representatie gebruiken. In het voorbeeld van de turtle op het Canvas: de opdrachten voor het Canvas gaan uit van een rechthoekig coördinatenstelsel met de oorsprong (0,0) linksboven.


## Representatie bij het oplossen van problemen

Een probleem kan eenvoudiger op te lossen zijn bij het gebruik van een bepaalde representatie.

* voor de turtle is een lokaal polair coördinatenstelsel het meest natuurlijke. Voor een robot-turtle hoeven we dan verder niets te doen. Voor een turtle die het Canvas gebruikt moeten we de beweging van de turtle omrekenen.
* sommige problemen met getallen zijn eenvoudiger op te lossen als we een lijst van priem-factoren als representatie gebruiken. Het vermenigvuldigen van twee getallen is dan eenvoudig het optellen van de priemfactoren.


## Overbruggen van de kloof tussen technologie en probleem

## Representatie en interpretatie; betekenis

