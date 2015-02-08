# Enkelvoudige waarden

We hebben in de voorbeelden tot nu toe, naast functies, ook *getallen* gebruikt. Een getal is een voorbeeld van een *waarde*.

In dit hoofdstuk behandelen we voorbeelden van enkelvoudige waarden: getallen en strings (tekenreeksen). Later zullen we andere enkelvoudige waarden tegenkomen, en samengestelde waarden.

Een waarde heeft in JavasScript een *type*: van een waarde kun je opvragen of dit bijvoorbeeld een `number` is, of een `string`.

De bewerkingen (operatoren en functies) die voor numbers verschillen van die van strings. Soms heeft eenzelfde operator-symbool een heel andere betekenis.

> de `+`-operator voor numbers staat voor optelling; voor strings betekent dit aaneenrijgen (concatenatie).gebruik je eenzelfde operatorje kunt uitvoeren met numbers zijn andere dan die v

## Number

Een `Number` is een geheel getal, of een drijvende-komma getal, beide in een beperkt bereik:

Gehele getallen in het bereik -XX tot XX worden precies voorgesteld; voor grotere of kleinere getallen heb je te maken met een verlies aan precisie.

Een drijvende-komma getal is een getal zoals je dat ook op een rekenmachine vindt. Zo'n getal heeft ook een beperkte precisie. Voor onze doeleinden is dat meestal geen probleem, maar voor ingewikkelde Wiskundige of Natuurkundige berekeningen moet je rekening houden met afrondfouten en dergelijke. Er is een heel vakgebied in de Wiskunde aan dergelijke problemen gewijd: Numerieke Wiskunde.

> Computers kunnen alleen met een eindige representatie van getallen werken. "reële getallen" kun je daarom niet als waarde voorstellen (tenzij je accepteert dat berekeningen oneindig lang kunnen duren).


## Onderscheid tussen Number en String

Je moet in je programma weten wanneer je met een number te maken hebt, en wanneer met een string. Als je deze door elkaar gebruikt, kun je voor verrassingen komen te staan:

* `3 + 4 + 5` -> 12 (number)
* `"3" + 4 + 5` -> "345" (string)
* `3 + 4 + "5"` -> "75" (string)

* vgl. ook probleem in spreadsheet

