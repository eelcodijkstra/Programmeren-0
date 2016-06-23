# Herhaling

Door *herhaling* kunnen we in een beknopt algoritme een langlopend proces beschrijven. We kennen in de algoritmen in het dagelijks leven al verschillende vormen van herhaling:

* In de muziek komt herhaling op allerlei manieren voor. Je hebt meerdere notaties om een volledige herhaling te beschrijven: herhalen van de vorige maat, herhalingshaken om het deel tussen de haken te herhalen, "da capo" (vanaf het begin), enz.
* Een breipatroon zonder een notatie voor herhaling zou even groot worden als de trui die dit patroon beschrijft. Je hebt hier ook notaties voor *geneste herhaling* een constructie die zelf uit een herhaling bestaat.
* In recepten heb je op verschillende manieren te maken met herhaling: je kunt een recept maken voor meerdere personen ("pannekoeken"); ingrediënten komen vaak herhaald voor ("3 eieren"); je moet eiwit kloppen totdat dit stevig is; enz.

Herhaling is voor computerprogramma's essentieel: in de herhaling zit de kracht. Computers zijn enorm snel: een programma van 1000 regels zonder herhaling is in een miljoenste seconde al klaar.

Met de functie-notatie die we tot nu toe geleerd hebben kunnen we al eenvoudige vormen van herhaling maken, waarmee we computers lang bezig kunnen houden. Programmeertalen hebben meer mogelijkheden om herhaling uit te drukken: daarvan zullen we later meer mogelijkheden zien.

We kunnen verschillende vormen van herhaling onderscheiden:

* vaak is *vooraf bekend* hoe vaak iets herhaald moet worden: om een vierkant te tekenen, teken je 4 maal een zijde;
* als je te maken hebt met een reeks (verzameling) van objecten, dan kun je een actie uitvoeren op *alle objecten in de reeks*.
* in andere gevallen herhaal je een actie totdat je een bepaalde toestand bereikt hebt (vgl. het kloppen van eiwit).

In de voorbeelden in dit hoofdstuk beperken we ons tot de *bepaalde herhaling* ("herhaal n keer"): vóór de herhaling is bepaald hoe vaak deze herhaald moet worden 

## Voorbeeld: tekenen van een vierkant

Voor de *bepaalde herhaling* gebruiken we een functie die een meegegeven functie een aantal malen aanroept:

```js
function repeat(n, f)
```

De aanroep `repeat(4, side)` waarbij `side` een functie is komt overeen met: `side(); side(); side(); side();`.

We definiëren een functie `side60` waarmee we een zijde van het vierkant tekenen van 60 stappen (pixels) groot:

```js
function side60() {
  forward(60);
  right(90);
}
```

Hiermee kunnen we een vierkant tekenen:

```js
repeat(4, side60);
```

We merken bij dit voorbeeld het volgende op:

We kunnen op deze manier alleen maar een vierkant tekenen van een vaste grootte. Voor elke grootte moeten we een nieuwe functie `sideXXX` definiëren. Dat is erg omslachtig.

De functie `side60` bestaat uit twee elementen:

1. het tekenen van de zijde
2. het positioneren van de turtle voor de volgende zijde

Dit is een patroon dat we bij herhalingen vaak tegenkomen: naast de actie die het eigenlijke werk doet, heb je een actie nodig voor de overgang naar de volgende stap in de herhaling.

Voor deze herhaling hebben we een belangrijke eigenschap: voorafgaand aan elke stap staat de turtle in de juiste positie. Dit geldt voor elke stap, ook voor de eerste: daarom noemen we een dergelijke eigenschap een *invariant* van de herhaling. Op dit begrip komen we later nog uitgebreid terug.

## Voorbeeld: tekenen van een vierkant

In het vorige voorbeeld konden we alleen een vierkant tekenen met een vaste grootte: voor elke grootte moeten we een nieuwe functie `sideXXX` definiëren. We willen dit generaliseren tot een functie voor een willekeurig vierkant. En later mogelijk zelfs tot een willekeurig n-kant.

We willen een functie definiëren van de vorm: `function square(size) {...}`, voor het tekenen van een vierkant van willekeurige grootte. We maken gebruik van de herhalingsfunctie `repeat`:

```
function square(size) {
  repeat(4, side);
}
```

Voor het tekenen van een zijde moeten we een functie maken van de form: `function side() {...}` De grootte van de zijde kunnen we niet als parameter aan deze functie meegeven: `repeat` verwacht een functie zonder parameters.

> Dat is niet helemaal waar: in het gedeelte over rangnummers gaan we daar dieper op in.

Dit betekent dat we in de functie `side` gebruik moeten kunnen maken van de parameter `size` van de functie `square`. *Dit kan als we de functie `side` definiëren binnen de functie `square`*:

```
function square(size) {

  function side() {
    forward(size);
    right(90);
  }
  
  repeat(4, side);
}
```

We maken hier gebruik van de *scope-regel*: als een naam niet gedefinieerd is in de huidige functie, gebruik dan de definitie deze naam in de tekstueel omvattende functie (of in de globale naamruimte).

> In dit geval wordt `size` niet gedefinieerd in de functie `side`. Deze functie is gedefinieerd binnen de functie `square`: gebruik dan de definitie van `size` in `square` - met andere woorden: de parameter `size` van `square`.

In het hoofdstuk Namen en scope gaan we dieper in op deze regel.

## Lege herhaling

Als je voorafgaand aan de herhaling al het uiteindelijke resultaat bereikt hebt, voer je de acties in de herhaling niet uit. We noemen dit ook wel een lege herhaling. Voorbeeld: `repeat(0, edge)`.

Deze lege herhaling is een bijzonder geval waar we altijd rekening mee houden. Voorbeeld: als je een rij getallen ter lengte 0 moet optellen, is de som 0.


## Geneste herhaling

We kunnen een opdracht met herhaling zelf ook weer herhalen. We spreken dan over een geneste herhaling.

We kunnen dit demonstreren met een aantal figuren:

Een vlak met vierkanten: een rij is een herhaling van 4 vierkanten, het vlak bestaat uit 3 rijen.

## Herhaling met rangnummer

Soms hangt de herhaalde actie af van het rangnummer van de herhaling: de eerste rij bevat 1 vierkant, de tweede rij 2 vierkanten, enzovoorts.

In de informatie beginnen we altijd met rangnummer 0. Dit zorgt voor meer regelmaat in de programma's, en vermindert de kans op fouten. Het is in het begin even wennen, maar na verloop van tijd merk je de voordelen hiervan.









