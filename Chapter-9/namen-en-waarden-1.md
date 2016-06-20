## Namen en naamsconflicten

We gebruiken namen om de definitie te kunnen koppelen aan het gebruik: denk bijvoorbeeld aan functies en parameters.

> Dit gebruik van namen is niet uniek in de Informatica: ook in het dagelijks leven gebruiken we namen om te kunnen verwijzen. We benoemen mensen en dingen, van concreet ("stoel") tot abstract ("vrijheid"). We moeten dan wel een manier hebben om uit te vinden waarnaar een naam verwijst. Voor een naam als "de rector" kijken we in het organisatieschema van de school. Voor een naam als "transistor" kijken we het woordenboek of een encyclopedie.

Voor computers maakt het niet uit welke naam je kiest: een naam van de vorm `x13548503783958` is voor een computer geen probleem. Maar een programma moet ook door mensen gelezen en begrepen kunnen worden. Dan is het belangrijk dat we aan een naam kunnen zien wat deze betekent.

> In de Wiskunde heb je meestal genoeg aan namen als *x* en *y*, en een klein aantal speciale namen als *sinus* of *Bessel-functie*. In de Informatica moeten we zoveel verschillende zaken benoemen dat dit principe niet meer werkt.

Dit betekent dat we een grote vrijheid willen hebben in het kiezen van een naam voor bijvoorbeeld een functie of een parameter.

* vrij zijn in de keuze van de lokale namen, bijvoorbeeld de namen van de parameters van een functie;
* programma-delen van verschillende bronnen kunnen combineren. In het geval van Javascript hebben we bijvoorbeeld te maken met de standaard-bibliotheek (JavaScript library, met bijvoorbeeld `Math`), de namen die in de browser-omgeving gebruikt worden (zoals `document`), en libraries als jQuery (met een naam als `$`).

JavaScript hanteert voor namen onder meer de volgende regels:

* de lokale namen in een functie moeten uniek zijn; dit betekent dat de namen van de parameters in een functie allemaal verschillend moeten zijn;
* de lokale namen in een functie mogen gelijk zijn aan namen buiten de functie; een naam heeft altijd de meest lokale betekenis.

Je kunt de betekenis van een naam (welke definitie geldig is op een bepaald punt in de programmatekst) altijd vinden door in de programmatekst "van binnen naar buiten te zoeken". Omdat deze koppeling tussen naam en betekenis gekoppeld is aan de programmatekst heet dit *lexical scope*.

### Welke declaratie hoort bij welk gebruik van een naam?

* lexical scope

De definitie van een naam in een programma noemen we ook wel de *declaratie*. Alle andere plaatsen waar een naam voorkomt noemen we het *gebruik* van die naam. Een belangrijke vraag als we het gebruik van een naam tegenkomen in een programma is: welke declaratie hoort hierbij? Je kunt dit ook anders bekijken: waar is de declaratie van een naam geldig? Het geldigheidsgebied van een declaratie noemen we ook wel de *scope*.

Deze vraag kunnen we (voor de huidige programmeertalen) beantwoorden op grond van de (statische) programmatekst. We hoeven ons niet af te vragen hoe het (dynamische) proces eruit ziet. In een taal als JavaScript hebben we te maken met *lexicale scope*.

In JavaScript geldt de volgende regel: de declaratie van een naam is geldig vanaf het begin van de functie waarin deze declaratie staat, tot aan het eind van deze functie, met uitzondering van die lokale functies waarin dezelfde naam opnieuw gedeclareerd wordt. Dit noemen we ook wel *function scope*.

Voor namen die op het globale niveau gedeclareerd worden geldt dezelfde regel, als je dit niveau als een functie beschouwt.

Dit betekent dat je de betekenis van een naam "van binnen naar buiten" zoekt:

* als je het gebruik van een naam tegenkomt, zoek je eerst naar een declaratie in de functie waar dit gebruik voorkomt;
* als binnen deze functie de naam niet gedeclareerd wordt, zoek je in de omvattende functie;
* enzovoorts, totdat je op het buitenste (globale) niveau uitkomt.
* (als de naam daar niet voorkomt, en het is geen naam die in de taal gedefinieerd is (zoals `String` of `Math`), dan is er sprake van een programmeerfout.)

> Merk op dat je namen die in de taal gedefinieerd zijn, zoals `String` of `Math`, in principe een nieuwe betekenis kunt geven. Maar dat is wel een heel erg onverstandige manier van werken.

op de volgende manier de betekenis van een naam zoekt:

*

Merk op dat we deze regel al gebruikt hebben voor de functies en parameters die we eerder gezien hebben:

* als je in een functie een aanroep van een functie tegenkomt, zoek je de betekenis van die naam

## Functies binnen functies

De kracht van deze regels wordt duidelijk als we functies ook binnen functies kunnen declareren.

> In JavaScript zijn functies "first class citizens": alles wat met een eenvoudige waarde kan, zoals met een getal, kan ook met een functie. We zullen later zien dat dit een erg krachtig middel is.




Voorbeelden:






welke declaratie hoort bij het gebruik van een naam op een bepaalde plek in het programma

Waar vind je de definitie van een naam? Je zoekt in de programmatekst "van binnen naar buiten".

* in dezelfde functie
* in de omvattende functie
* in de omvattende functie van de omvattende functie (enz.)
* op het globale niveau (globale namen, globale variabelen)

In JavaScript geldt niet de regel dat je een naam moet definiëren voordat je deze kunt gebruiken. In het bijzonder kun je een functie gebruiken voordat je de definitie daarvan tegengekomen bent. Maar zoiets maakt het lezen van een programma lastig. Wij hanteren dan ook de regel (afspraak) dat je een naam moet definiëren voordat je deze kunt gebruiken ("define before use").

> Er zijn situaties waarin dit wat lastig wordt, bijvoorbeeld bij wederzijdse recursie.

Merk op dat we deze techniek ook gebruiken voor de namen van functies: als we de definitie van een functie niet vinden in de huidige functie, dan zoeken we in het omvattende blok.

En wat als we een parameter dezelfde naam geven als een functie (of een parameter) in een omvattend blok?

> Je kunt dit gebruik van lokale namen ook vergelijken met het gebruik van namen in je omgeving. Als je het over Jan hebt, dan bedoel je in eerste instantie de Jan die in dezelfde ruimte is, bijvoorbeeld het klaslokaal. Als er in de klas geen Jan is, maar er is maar één Jan op school, dan weet waarschijnlijk ook iedereen wie je bedoelt.

Een nieuw aspect is dat we ook functies binnen functies kunnen definiëren. Functies zijn in JavaScript "first class citizens". Dit betekent dat je overal waar je een waarde kunt gebruiken, je ook een functie-waarde kunt gebruiken: als variabele, als parameter, als property van een object, en als functie-resultaat.

### Hoe koppel je een naam aan een betekenis?

* declaratie van een naam (variabele-declaratie; parameter; functie-definitie)

Er is verschil tussen de declaratie van een naam (variabele), en de koppeling van een naam aan een waarde (toekenning, assignment).

* eigenlijk is daarbij sprake van betekenis op verschillende niveaus: de invariante betekenis van een naam - bijvoorbeeld: som; en de actuele waarde van een naam (variabele): de som van de rij getallen tot nu toe.

## Opmerkingen

Met een definitie (of declaratie) koppel je een naam aan een betekenis.

Voorbeelden:

```js
function succ(i) {
  return i + 1;
}

var x = 100;
let y = x * 2;
```

Met een naam kun je vervolgens verschillende dingen doen:

* je kunt deze *gebruiken* - bijvoorbeeld: het gebruik van een parameter of variabele in een expressie; of de aanroep van een functie. In deze gevallen gebruik je de betekenis die aan de naam gekoppeld is.
* je kunt deze doorgeven - bijvoorbeeld als parameter, of als element (property) van een object.
* (In dit geval is de actuele waarde niet altijd van belang; maar wel de betekenis op een hoger abstractieniveau.)
* 

