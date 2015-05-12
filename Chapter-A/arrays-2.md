## Arrays: vervolgonderwerpen

Bij het programmeren spelen arrays een belangrijke rol. In dit hoofdstuk geven we enkele voorbeelden van het gebruik van arrays - in het bijzonder bij de constructie van programma's.

In een ander hoofdstuk gaan we in op het gebruik van arrays in toepassingen - bijvoorbeeld voor het modelleren van aspecten van het toepassingsdomein.

### Algoritmen gebaseerd op arrays

* zoeken: lineair zoeken (asymmetrisch splitsen)
* zoeken: binair zoeken (symmetrisch splitsen)

Voor het zoeken van het eerste element in een array dat aan een bepaalde voorwaarde voldoet.

> Binair zoeken kunnen we ook in andere datastructuren, in het bijzonder in een boom; maar dan legt de datastructuur min of meer vast hoe we deze doorlopen (voor een bepaalde waarde).

### Uitwisselen van ruimte en tijd: arrays als functie, cache

We kunnen een array ook beschouwen als een functie: een afbeelding van de index naar de bijbehorende waarde

Als we een bepaalde functiewaarde vaak moeten uitrekenen, kan het handig zijn om deze te bewaren, bijvoorbeeld in een array. 

```js
var fibCache = [1, 1];

function fib(n) {
 if (!fibCache[n]) {
    fibCache[n] = fib(n-1) + fib(n-2);
  }
  return fibCache[n];
}

```

### Arrays voor opbergen en terugzoeken van data

### Arrays voor het bufferen van data

Een andere toepassing betreft het gebruik van een array als buffer. In dit geval hebben we te maken met twee of meer processen die niet strikt in hetzelfde tempo werken. Een typisch voorbeeld hiervan is een producer-consumer relatie: het ene proces produceert items, het andere verwerkt deze. De fluctuaties in het tempo van de producent en van de consument kunnen we opvangen door middel van een buffer.

We kunnen alleen fluctuaties, tijdelijke verschillen in snelheid, opvangen. Voor een  verschil in de gemiddelde snelheid op langere termijn helpt geen eindige buffer.

We kunnen te maken hebben met een autonome producer: dit proces kunnen we dan niet stoppen als we de resultaten niet kunnen verwerken.

In andere gevallen kunnen we de producer stoppen, als de buffer vol dreigt te raken. 


### Arrays als basis voor datastructuren



#### Queue

Een *queue* of een LIFO (Last In First Out) lijst gebruik je bijvoorbeeld voor het bufferen van events: deze handel je vervolgens één voor één af, in volgorde van binnenkomst.

In het geval van JavaScript kun je de `push` operatie gebruiken om een nieuw element toe te voegen, en de `shift` operatie om het oudste element te verwijderen:

```js
var lifo = ["event10", "event11"];
lifo.push("event12");
var ev = lifo.shift();
```

Als je te maken hebt met een buffer van vaste grootte, gebruik je twee pointers (indices) in deze buffer, om de eerste vrije plaats en het eerst te verwijderen element aan te geven. Als deze twee gelijk zijn, dan is de buffer leeg.

Ook voor het schedulen van processen gebruik je vaak een queue. De "ready queue" bevat de processen die niet geblokkeerd zijn, maar die ook nog niet aan een (de?) processor toegewezen zijn.

Je kunt ook een event-queue hebben met een andere *policy*, waarin bepaalde events voorrang (prioriteit) hebben boven andere. In zo'n geval spreek je over een *priority queue*. Dit is een veel lastiger datastructuur dan een simpele LIFO-queue.

### Dictionaries en associatieve arrays

Een klassiek arrays heeft een aaneeengesloten reeks gehele getallen als index. In veel talen ligt het indexbereik bovendien vast bij de declaratie van het array.

Voor sommige toepassingen willen we gegevens niet opslaan en opzoeken aan de hand van een getal, maar bijvoorbeeld aan de hand van een naam (string), of eventueel aan de hand van een willekeurig object. Een array met strings als index noemen we ook wel een *dictionary*.

Een typisch voorbeeld van het gebruik hiervan is als we willen tellen hoe vaak de woorden in een tekst voorkomen. Elk woord is dan een index in dit array.

In het geval van een dictionary willen we het indexbereik ook dynamisch kunnen uitbreiden, als we een nieuwe naam of "key" tegenkomen.

Een dictionary is een voorbeeld van een (name, value) of een (key, value) geheugen. Bij elke naam die als index gebruikt kan worden, hoort (hooguit) één naam. We kunnen bovendien alle keys opsommen - zodat we een herhaling over alle elementen in de dictionary kunnen doen.

Dit komen we op veel plaatsen in de ICT tegen:

* `localStorage` is een voorbeeld van een (key, value) geheugen; zowel de key als de value zijn in dit geval strings.
* sommige databases hebben het karakter van een (key, value) geheugen.
