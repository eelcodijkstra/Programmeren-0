# Objecten via functies

> Het onderstaande beschrijft een "functionele" manier om objecten te maken. Deze aanpak is ontleend aan een beschijving van Douglas(?) Crockford (zie YouTube video). Hij noemt dit ook wel "class-less objects".

Het typische voorbeeld is:

```js
function constructor(spec) {
  var
    that = anotherConstructor(spec),
    member,
    method = function () {
      // use that, member, method(s)
    };
    
  that.method = method;  
  return that;    
}
```

> Ik zou `spec` eerder `pars` noemen: het zijn de parameters van de constructor.

Voordelen van deze aanpak

* de toestand van het object bestaat uit de lokale variabelen van de constructor: deze zijn alleen bereikbaar via de methods van het resultaat-object.
* je kunt de toegang tot de toestand zo precies regelen als je wilt.
* je kunt in de constructor hulpfuncties definiëren die toegang hebben tot de toestand en tot de andere functies en methodes. Deze hulpfuncties zijn niet bereikbaar buiten de constructor.

Voorbeeld:

```js
function newCounter(spec) {
  var
    initialValue = spec.value !== undefined ? spec.value : 0,
    value = initialValue;

  return {
    up: function () { value += 1; },
    down: function () { value -= 1; },
    value: function () { return value; },
    reset: function () { value = initialValue; }
  };
}

var myCounter = newCounter({value:10});
```

(Dit is weer een voorbeeld van het gebruik van anonieme functies: zo'n korte notatie heeft zeker zijn voordelen.)

Nadelen van deze aanpak:

* ruimte (bytes): je hebt te maken met tenminste twee objecten: (i) het activation object van de constructor; (ii) het resultaat-object met de methods. Daar komt eventueel nog het pars-object bij.
* er is geen sprake van inheritance?

Hoe realiseer je in dit geval inheritance? Hoe kun je gemeenschappelijk gedrag onderbrengen?

Dit blijkt uit het allereerste voorbeeld: zie het gebruik van `otherConstructor`.

```js
function makeGameObject(spec){
}

function makeBall(spec){
}
```

Wat zijn typische voorbeelden van inheritance?

* grafisch object: hierbij gaat het onder andere om de virtuele functies: elk grafisch object heeft een `draw` functie; bij het samenstellen van een grafische object uit andere objecten hoef je geen case-analysis te doen.
    * dit is grotendeels een kwestie van afspraak: je kunt er altijd voor zorgen dat een grafisch object een `draw` functie heeft.
    * maar het helpt als de taal het maken van afspraken ondersteunt - en waarschuwt als je je er niet aan houdt.
    
Er zijn veel voorbeelden van *patronen* die je met objecten (en functies) vorm kunt geven.

> Ik begrijp dat in de volgende versie van JavaScript de constructie: `{abc: abc, def: def, ...}` afgekort kan worden tot: `{abd, def, ...}`.