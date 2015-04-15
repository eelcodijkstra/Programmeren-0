Als voorbeeld van verdeel en heers behandelen we het sorteren van een rij getallen. Deze rij kan de vorm hebben van een array, of van een lijst.

Voor de "binaire" vorm van verdeel en heers splitsen we de rij in twee (ongeveer) even grote deelrijen. Deze deelrijen sorteren we (op dezelfde manier). De resultaten combineren we dan weer tot een oplossing voor het oorspronkelijke probleem:

1. Splits de rij R in R0 en R1
2. Sorteer R0 tot R0' en R1 tot R1'
2. Combineer R0' en R1' tot R': een gesorteerde versie van R

We kunnen de rij R voor dit doel op twee manieren splitsen. We kunnen het splitsen eenvoudig houden: we moeten dan bij het combineren extra werk doen. Of we maken meer werk van het splitsen: we kunnen eenvoudig combineren. Dit geeft aanleiding tot twee verschillende sorteeralgoritmen, die ongeveer even efficiënt zijn.

*Merge sort*:

1. Splits de rij R in twee opeenvolgende segmenten van vrijwel gelijke lengte: R0 + R1 = R.
2. Sorteer R0 tot R0' en R1 tot R1'.
3. Combineer R0' en R1', door steeds het kleinste elemenent van de resten van R0' en R1' te verplaatsen naar de staart van R'. (de "merge")

*Quicksort*:

1. Neem een (willekeurig) element P uit de rij R. Splits de rij R in alle elementen die <= P zijn (R0), en alle elementen die >P zijn (R1).
2. Sorteer R0 tot R01 en R1 tot R1'.
3. Combineer R' uit de opeenvolging (contatenatie) van R0' en R1': R' := R0' + R1'

Een dergelijk patroon komen we in meer gevallen tegen: doe je het meeste werk bij het splitsen, om het samenvoegen eenvoudig te houden; of juist omgekeerd?

> Kan ik andere voorbeelden hiervan geven?

## Andere voorbeelden

* sommeren van alle getallen van 0..99 (volgens de aanpak van Euler).
* binair zoeken: gebruik van ordening ("gesorteerd").

Soms kom je ook een andere variant tegen: door meer energie te steken in het analyseeren van het probleem (vgl. Euler), kun je met een eenvoudiger algoritme volstaan - of zelfs met een analytische oplossing.


