## Namen en naamsconflicten

We hebben gezien dat het handig (essentieel?) is om waarden namen te geven. Voor computers maakt het niet uit welke namen je kiest: een naam van de vorm `x13548503783958` is voor een computer geen probleem. Maar programma's moeten ook door mensen gelezen en begrepen kunnen worden. Dan is het belangrijk om begrijpelijke namen te gebruiken. Waar mogelijk willen we aan de naam ook kunnen zien wat deze betekent.

Een gevolg is dat we redelijk vrij willen zijn in de keuze van de namen in een programma. We willen in het bijzonder:

* vrij zijn in de keuze van de lokale namen, bijvoorbeeld de namen van de parameters van een functie;
* programma-delen van verschillende bronnen kunnen combineren. In het geval van Javascript hebben we bijvoorbeeld te maken met de standaard-bibliotheek (JavaScript library, met bijvoorbeeld `Math`), de namen die in de browser-omgeving gebruikt worden (zoals `document`), en libraries als jQuery (met een naam als `$`).

JavaScript hanteert voor namen onder meer de volgende regels:

* de lokale namen in een functie moeten uniek zijn; dit betekent dat de namen van de parameters in een functie allemaal verschillend moeten zijn;
* de lokale namen in een functie mogen gelijk zijn aan namen buiten de functie; een naam heeft altijd de meest lokale betekenis.

Je kunt de betekenis van een naam (welke definitie geldig is op een bepaald punt in de programmatekst) altijd vinden door in de programmatekst "van binnen naar buiten te zoeken". Omdat deze koppeling tussen naam en betekenis gekoppeld is aan de programmatekst heet dit *lexical scope*.

### Welke naam hoort bij welke betekenis?

* lexical scope

### Hoe koppel je een naam aan een betekenis?

* declaratie van een naam (variabele-declaratie; parameter; functie-definitie)

Er is verschil tussen de declaratie van een naam (variabele), en de koppeling van een naam aan een waarde (toekenning, assignment).

