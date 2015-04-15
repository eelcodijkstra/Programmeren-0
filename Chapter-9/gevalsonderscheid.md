# Gevalsonderscheid

* wanneer is er in het probleem sprake van gevalsonderscheid?
* bijvoorbeeld bij randgevallen (grensgevallen)
* zoeken
* sorteren
* filteren

Wanneer gebruik je voorwaarden in spreadsheets?

* filteren
* aanpassen van de weergave

Dankzij IF kun je:

* reageren op input: actie laten afhangen van de invoer (of van de context);
* actie laten afhangen van de interne toestand (nb: dit is eigenlijk alleen zinvol als er sprake is van invoer)
* 

NB: bij muziek of bij speeldozen enz. is er geen sprake van IF - wel van herhaling, en eventueel van procedures/functies.

Wat zijn geschikte voorbeelden voor de inleidende cursus?

* random walk: afhankelijk van een random getal kies je een cirkel, een vierkant, een driehoek, een lijn, of een draaiing.
    * je hebt de IF nodig om onderscheid te maken tussen de verschillende vormen. Voor een pure random walk heb je geen IF nodig.
* botsing van turtle met: randen van de wereld, of eventueel met bepaalde objecten.
* verwerken van invoer: bijvoorbeeld 3=driehoek, 4=vierkant, 100=cirkel, 2=lijn. (Dit kunnen we doen in een functie die aan een button gekoppeld is.)

## Grensgevallen

We gebruiken een if-statement vaak om grensgevallen af te handelen. In het geval van de turtle is bijvoorbeeld het raken van de grens van het Canvas (de "turtlewereld") iets waar we een speciale opdracht aan kunnen koppelen. In de voorbeelden die we tot nu toe gezien hebben trekt de turtle zich van deze grens niets aan: de turtle verdwijnt dan buiten het Canvas. Je kunt in dit geval de turtlewereld zien als onbegrensd en oneindig. De volgende soorten acties komen overeen met een andere wereld:

* als de turtle een grens bereikt, kaatst deze terug - zoals bijvoorbeeld een biljartbal op een biljart; de wereld is begrensd en eindig;
* als de turtle een grens bereikt, komt deze aan de andere kant te voorschijn. De wereld van de turtle komt dan overeen met een *torus* (een "doughnut"). De wereld is onbegrensd maar eindig.

In de programmeervoorbeelden kun je beide verder uitwerken.

Je kunt ook te maken hebben met andere soorten grensgevallen. Deling is een bekend voorbeeld:  bij $$a / b$$, voor gehele getallen $$a$$ en $$b$$, trek je $$b$$ net zo vaak van $$a$$ of totdat er een rest $$0 <= r < a$$ overblijft. Dit betekent dat je steeds moet testen (if) of je nog een stap kunt doen.

> Voor vermenigvuldigen heb je een dergelijke test niet nodig.

## Botsingen

Ee turtle kan ook tegen andere voorwerpen botsen. Dit speelt vooral als we computergames willen maken: de verschillende spelers en voorwerpen kunnen op allerlei manieren botsen. We moeten in de eerste plaats detecteren of er een botsing plaatsvindt; als dit gebeurt ("if"), dan moeten we een bijbehorende actie uitvoeren.

## 