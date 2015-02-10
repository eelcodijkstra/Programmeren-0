# Statisch en dynamisch

Bij het programmeren spring je voortdurend heen en weer tussen twee manieren van kijken: de statische kijk: de programmatekst; en de dynamische kijk: het proces.

Vergelijk het programma:

```js
function edge(size) {
  forward(size);
  right(90);
}

function square(size) {
  edge(size);
  edge(size);
  edge(size);
  edge(size);  
}

square(20);
square(30);
square(40);
```

en het proces:

```js
forward(20);
right(90);
forward(20);
right(90);
forward(20);
right(90);
forward(20);
right(90);
forward(30);
right(90);
forward(30);
right(90);
forward(30);
right(90);
forward(30);
right(90);
forward(40);
right(90);
forward(40);
right(90);
forward(40);
right(90);
forward(40);
right(90);
```

Met een programma van een tiental regels kun je een proces maken van miljarden opdrachten of meer.