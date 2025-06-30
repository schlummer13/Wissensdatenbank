# 🔀 Arrays sortieren

Die Methode `sort()` wird verwendet, um Elemente eines Arrays zu sortieren. Sie kann **alphabetisch, numerisch oder nach benutzerdefinierten Regeln** sortieren.

---

## 📌 Standardverhalten

```js
let namen = ["Max", "Anna", "Zoe"];
namen.sort(); // ["Anna", "Max", "Zoe"]
```

### ⚠️ Vorsicht bei Zahlen!

```js
let zahlen = [10, 2, 5];
zahlen.sort(); // ["10", "2", "5"] → wird als STRING sortiert!
```

> 🔧 Lösung: Eigene Vergleichsfunktion verwenden!

---

## 🧮 Numerisch sortieren (aufsteigend & absteigend)

```js
let zahlen = [10, 2, 5];

// Aufsteigend
zahlen.sort((a, b) => a - b); // [2, 5, 10]

// Absteigend
zahlen.sort((a, b) => b - a); // [10, 5, 2]
```

---

## 🔡 Zeichenketten alphabetisch sortieren

```js
let namen = ["Zoë", "Anna", "Änne"];

// Standard
namen.sort(); // ["Anna", "Zoë", "Änne"]

// Richtig mit localeCompare (inkl. Umlaute etc.)
namen.sort((a, b) => a.localeCompare(b)); // ["Anna", "Änne", "Zoë"]
```

---

## 🔁 Objekte sortieren nach Eigenschaft

```js
let personen = [
  { name: "Tom", alter: 30 },
  { name: "Anna", alter: 25 },
  { name: "Luca", alter: 28 }
];

// Nach Alter
personen.sort((a, b) => a.alter - b.alter);
/*
[
  { name: "Anna", alter: 25 },
  { name: "Luca", alter: 28 },
  { name: "Tom", alter: 30 }
]
*/
```

---

## 🔄 Sortierte Kopie mit `toSorted()` (ab ES2023)

```js
let zahlen = [3, 1, 4];
let sortiert = zahlen.toSorted(); // [1, 3, 4]
console.log(zahlen); // Original bleibt [3, 1, 4]
```

---

## 🧩 Mit `.reverse()` kombinieren

```js
let wochentage = ["Montag", "Dienstag", "Mittwoch"];
wochentage.reverse(); // ["Mittwoch", "Dienstag", "Montag"]
```

Oder:

```js
let zahlen = [1, 2, 3];
zahlen.sort((a, b) => b - a); // direkt absteigend
```

---

## 🧠 Tipps

- Die `sort()`-Methode **verändert** das Original-Array!
- Verwende `toSorted()` für **nicht-destruktive Sortierung**
- Verwende `localeCompare()` für korrekte Sprach-Sortierung

---

## 🧪 Mini-Projekt: Sortierung eines Todo-Arrays

```js
const todos = [
  { text: "Einkaufen", prio: 2 },
  { text: "JavaScript lernen", prio: 1 },
  { text: "Fitness", prio: 3 }
];

todos.sort((a, b) => a.prio - b.prio);
console.log(todos);
```
