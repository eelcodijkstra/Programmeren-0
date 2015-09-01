# Programma, processor, proces, en resultaat

> Enkele begrippen rond programmeren komen we ook in het dagelijks leven tegen. Deze voorbeelden kunnen helpen om programmeren beter te begrijpen.

Als je een taart wilt bakken, heb je een *recept* nodig. In het recept staat wat je nodig hebt: de ingrediënten (bijvoorbeeld bloem en boter), en de hulpmiddelen (zoals een kom, een mixer, en een oven). Het recept geeft stap voor stap aan hoe je van de ingrediënten, met deze hulpmiddelen, een taart bakt.

Met een recept alleen gebeurt er nog niets: je hebt een *kok* nodig - iemand nodig die het recept kan uitvoeren. Deze heeft de *hulpmiddelen* nodig, en de *ingrediënten*. Daarna kan deze aan de slag gaan met het bakken van de taart. Het uitvoeren van de verschillende stappen van het bakken kost *tijd*. We noemen iets dat in de tijd verloopt een *proces*.

Als alles goed gaat, heb je als *resultaat* van het bakken een taart. Aan de taart kun je niet meer zien hoe deze gemaakt is - welke stappen er gebruikt zijn. Maar als je de taart wilt gebruiken (opeten) is dat ook niet je eerste vraag.

We hebben in dit voorbeeld te maken met de volgende begrippen:

* *script* (programma) - stappenplan dat precies vastlegt welke stappen uitgevoerd moeten worden;
* *actor* (processor) - kan een script uitvoeren; dit kan een mens zijn, maar ook een machine (automaat);
* *proces* - het uitvoeren van een script door een actor; bij een proces is er meestal sprake van:
* *invoer* (input)
* *uitvoer* (output, resultaat)
* *hulpmiddelen* (resources)

In het dagelijks leven vinden we meer voorbeelden van scripts, actoren en processen:

| Script/Programma   | Proces | Actor/Processor |Resultaat |
| ---         | ---    | ---       | ---      |
| Recept      | Bakken | Kok       | Taart    |
| Breipatroon | Breien | Herder    | Trui     |
| Routebeschrijving | Reis    | Automobilist | Bestemming bereikt |
| Orgelboek   | Afspelen | Draaiorgel | Muziek |
| Optellen    | Rekenen | Boekhouder | Totaal     |

De verschillende *scripts* zijn geschreven voor een bepaald soort *actor*. Een recept is geschreven in een taal die door een kok begrepen wordt. Als je wilt leren koken, dan moet je de recepten-taal (of koks-taal) leren begrijpen.

Een script of programma voor een computer schrijven we in een *programmeertaal*. Dit script legt precies en volledig vast welke stappen de computer moet nemen bij het uitvoeren van het proces.

Een computer voert de opdrachten in het programma uit precies en letterlijk uit. Een computer doet wat je zegt - en dat is misschien niet altijd wat je bedoelt. En omdat computers zo snel zijn, loopt het soms erg snel uit de hand.

> Vb: (i) peanut butter jelly sandwich; (ii) tovenaarsleerling.

## Programma's zonder invoer

Als een draaiorgel een orgelboek afspeelt, komt daar verder geen invoer aan te pas. Dit betekent ook dat het resultaat (met hetzelfde orgel) ook altijd precies gelijk is. Het systeem is programmeerbaar - met een ander programma krijg je een ander resultaat.

Andere voorbeelden van programma's die gebruikt worden om een apparaat te besturen:

* het [Jaquard weefgetouw](http://nl.wikipedia.org/wiki/Jacquardgetouw): het programma, op een stel ponskaarten, beschrijft het patroon dat geweven moet worden. Dit is een ingenieus systeem - één van de voorlopers van de huidige computers.
* dansende robot: je kunt ee robot een dans laten uitvoeren, je beschrijft dan precies welke danspassen de robot uit moet voeren; de robot reageert niet op de muziek, of op andere invoer, maar voert precies het dansprogramma uit;
* verfrobot: sommige robots kunnen hun acties uitvoeren zonder invoer: ze maken altijd precies dezelfde bewegingen, hoe de omgeving er ook uitziet.

## Programma's met invoer

De voorbeelden die we hiervoor gezien hebben geven bij hetzelfde programma altijd hetzelfde resultaat. Als het ook mogelijk is om invoer te verwerken neemt het aantal praktische mogelijkheden enorm toe. Eenzelfde programma kan dan resulteren in totaal verschillende processen en resultaten.

Een zakrekenmachine is een voorbeeld van een processor met een vast programma dat reageert op invoer: de getallen en opdrachten die je via het toetsenbord invoert.

Bij de meeste computerprogramma's is er sprake van invoer. Het verloop van het programma (het proces) wordt dan bepaald door het programma en door de waarden in de invoer (data). Deze data kan uit verschillende bronnen afkomstig zijn: bijvoorbeeld van de gebruiker, maar ook uit een bestand of uit een database.

> Neem als voorbeeld een tekstverwerkingsprogramma: in dit geval heb je te maken met het tekstbestand dan bewerkt wordt, en met de interactieve invoer van de gebruiker. Mogelijk kun je ook nog allerlei voorkeursinstellingen aangeven die in een apart bestand bewaard worden. Dit zijn allemaal voorbeelden van data die gebruikt worden bij de uitvoering van het programma.

> Als een programma anders reageert dan je gewend bent, hoeft dat niet aan het programma te liggen: het programma kan andere invoer gebruiken, bijvoorbeeld een bestand met voorkeursinstellingen, waardoor het gedrag verandert.

### Over processen

We gebruiken het begrip "proces" voor alles dat zich in de tijd afspeelt, waarbij er sprake is van *verandering*. "Tijd", "volgorde", "toestand" zijn begrippen die daar direct mee te maken hebben.

## Opmerkingen

#### Wanneer begint de uitvoering van een programma?

Eigenlijk moeten we naast programma, proces en resultaat nog een begrip invoeren: de *opdracht* om het programma uit te voeren. In de context van programmeren komt dat bijvoorbeeld overeen met een functie-aanroep.

Hoe ziet dit eruit in de voorbeelden uit het dagelijks leven?

In de browser is een knop (button) vaak gekoppeld aan een stukje programma (functie). Het indrukken van de knop, bijvoorbeeld door een muis-click, is dan de opdracht om dat stukje programma uit te voeren.

In het kook-voorbeeld kan de chef-kok zijn assistent de opdracht geven voor het bereiden van een gerecht aan de hand van een bepaald recept. Dan kan bijvoorbeeld zijn: "maak een kwart liter sauce bearnaise". In dit geval is het belangrijk dat het recept een naam heeft. De assistent weet dan wat er bedoeld wordt, en kan eventueel in het kookboek het recept opzoeken.

#### Programma en data

Het onderscheid tussen invoer en programma is niet fundamenteel - maar wel praktisch. In een universele Turingmachine - een wiskundig model van een universele computer - staat zowel de invoer als het programma op de band (tape); ook de tussenresultaten van de berekeningen komen daarop terecht. In een computer volgens de Von Neuman architectuur staan zowel de data (invoer en tussenresultaten) als het programma in hetzelfde geheugen.

Het is om meerdere redenen praktisch om programma en data (invoer en tussenresultaten) te scheiden:

* het programma staat van te voren vast, de invoer is soms pas tijdens de uitvoering van het programma beschikbaar. Dit is bijvoorbeeld het geval bij een interactief programma, zoals de genoemde tekstverwerker, of een computergame.
    * we zeggen dan ook wel dat het programma een ander "moment of binding" heeft dan de invoer;
* de invoer beschrijft het actuele *probleem* dat we willen oplossen; het programma beschrijft  de manier waarop we de oplossing willen berekenen.
    * we kunnen over een programma redeneren voor alle mogelijke invoer, en dus voor alle mogelijke voorbeelden van het probleem dat het programma moet oplossen.
* we kunnen een computersysteem beveiligen door te bewaken welke programma's in uitvoering genomen worden. We hoeven dan geen beveiliging op de data te hebben.





