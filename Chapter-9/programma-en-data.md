## Programma en data

Het onderscheid tussen invoer en programma is niet fundamenteel, maar wel praktisch. In een universele Turingmachine - een wiskundig model van een universele computer - staat zowel de invoer als het programma op de band (tape); ook de tussenresultaten van de berekeningen komen daarop terecht. In een computer volgens de Von Neuman architectuur staan zowel de data (invoer en tussenresultaten) als het programma in hetzelfde geheugen. Een Harvard-architectuur gebruikt verschillende geheugens voor programma (code) en data.

Het is om meerdere redenen praktisch om programma en data (invoer en tussenresultaten) te scheiden:

* het programma staat van te voren vast, de invoer is soms pas tijdens de uitvoering van het programma beschikbaar. Dit is bijvoorbeeld het geval bij een interactief programma, zoals de genoemde tekstverwerker, of een computergame.
    * we zeggen dan ook wel dat het programma een ander "moment of binding" heeft dan de invoer;
* de invoer beschrijft het actuele *probleem* dat we willen oplossen; het programma beschrijft  de manier waarop we de oplossing willen berekenen.
    * we kunnen over een programma redeneren voor alle mogelijke invoer, en dus voor alle mogelijke voorbeelden van het probleem dat het programma moet oplossen.
* we kunnen een computersysteem beveiligen door te bewaken welke programma's in uitvoering genomen worden. We hoeven dan geen beveiliging op de data te hebben.
