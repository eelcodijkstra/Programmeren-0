# Aanpak van problemen: verdeel en heers(1)

Het maken van een programma kun je doen met het *probleem* als uitgangspunt. Dit heet ook wel de *top-down* aanpak. Je kunt ook beginnen aan de kant van de technologie (programmeertaal, libraries, e.d.). In dat geval is er sprake van een *bottom-up* aanpak. Vaak gebruiken je  een combinatie van beide: soms top-down, soms bottom-up.

Bij de top-down aanpak is *verdeel en heers* een gebruikelijke strategie. Je splitst het probleem in twee of meer deelproblemen. Deze los je onafhankelijk van elkaar op. Vervolgens combineer je de deeloplossingen tot een oplossing voor het oorspronkelijke probleem.

Je moet de deeloplossingen samen kunnen voegen met de middelen die je in de programmeertaal hebt. De verschillenden manieren waarop je een probleem in deelproblemen kunt splitsen, hangen dus af van de manieren waarop je de deeloplossingen kunt samenstellen.

In dit hoofdstuk gebruiken we de *opeenvolging* als manier van samenstellen. Dit kun je gebruiken als er sprake is van *verschillende* (niet-gelijksoortige) deelproblemen.

Een voorbeeld is het tekenen van een huis: de deelvormen zijn een rechthoek en een driehoek. Voor deze deelvormen maken we afzonderlijks functies. Voor het tekenen van het huis combineren we deze door eerst de driehoek te tekenen, en dan de rechthoek (of omgekeerd: we kunnen beide volgordes kiezen).

Bij het combineren van deeloplossingen heb je vaak "lijm" nodig: extra opdrachten om de deeloplossingen aan te laten sluiten. In het geval van het huis bestaat deze uit het draaien van de turtle, voor en na het tekenen van de driehoek.

* splits het probleem in *verschillende* deelproblemen;
* splits het probleem in *gelijksoortige* deelproblemen.

## Lijm

Bij het combineren van deeloplossingen hebben we vaak wat extra code nodig. Dit kun je zien als de "lijm" om deze deeloplossingen te combineren tot een oplossing voor het oorspronkelijke probleem.

## Verschillende deelproblemen

Voorbeelden:

* tekenen van huis (met driehoeken en rechthoeken)
* tekenen van gezicht; verkeersborden

## Gelijksoortige deelproblemen

Voorbeelden:

* tekenen van een straat; bloem; boom

De manier van splitsen kan in dit geval een groot verschil maken:

* splitsen in twee vrijwel even grote deelproblemen (halveren: binair, logaritmisch)
* afsplitsen van een enkel element (lineair)

Soms is het handig om twee elementen af te splitsen. Voorbeeld: sommeren van een reeks opeenvolgende getallen.

(Wanneer is het halveren handig, en wanneer de lineaire aanpak?)

> De lineaire aanpak kunnen we gebruiken in een normale herhaling. Het halveren geeft altijd een recursieve oplossing: we splitsen het oorspronkelijke probleem op in een tweetal gelijksoortige maar kleinere problemen.

Een belangrijk onderdeel van herhaling is het vinden van de elementaire stap. Deze bestaat meestal uit twee delen: (i) de eigenlijke stap; (ii) de lijm, die nodig is om de volgende stap voor te bereiden.

Denk bijvoorbeeld aan het tekenen van een straat:

* de eigenlijke stap is het tekenen van een huis;
* de lijm is de verplaatsing van de turtle naar de positie van het volgende huis.

> In principe hebben we twee mogelijkheden: (a) we gebruiken de "lijm" voor de eigenlijke stap; (ii) de gebruiken de "lijm" na de eigenlijke stap. Wij hanteren hier meestal de tweede methode (om consequent te zijn?).


