# 🔍 Array Search (Suchen in Arrays)

JavaScript bietet verschiedene Methoden, um in Arrays gezielt nach **Werten, Positionen oder bestimmten Bedingungen** zu suchen.

---

## 📋 Übersicht

| Methode         | Zweck                                    | Gibt zurück           |
|------------------|-------------------------------------------|------------------------|
| `indexOf()`     | Position eines Werts finden               | Zahl (`-1` bei nicht gefunden) |
| `lastIndexOf()` | letzte Position eines Werts finden        | Zahl (`-1` bei nicht gefunden) |
| `includes()`    | Prüfen, ob ein Wert enthalten ist         | `true` oder `false`    |
| `find()`        | Erstes passendes Element finden           | Wert oder `undefined`  |
| `findIndex()`   | Index des ersten passenden Elements       | Index oder `-1`        |
| `some()`        | Prüfen, ob **ein** Element passt          | `true` oder `false`    |
| `every()`       | Prüfen, ob **alle** Elemente passen       | `true` oder `false`    |

---

## 🔢 `indexOf()` – Index eines Werts

```js
const farben = ["rot", "grün", "blau"];

farben.indexOf("grün");   // 1
farben.indexOf("gelb");   // -1 (nicht gefunden)
```

---

## 🔁 `lastIndexOf()` – Letzter Fund

```js
const zahlen = [1, 2, 3, 2, 1];

zahlen.lastIndexOf(2);    // 3
```

---

## ✅ `includes()` – Enthält der Array diesen Wert?

```js
let tiere = ["Hund", "Katze", "Vogel"];

tiere.includes("Katze");   // true
tiere.includes("Fisch");   // false
```

---

## 🔍 `find()` – Erstes Element nach Bedingung

```js
let zahlen = [5, 12, 8, 130, 44];

let gefunden = zahlen.find(n => n > 10);
console.log(gefunden); // 12
```

---

## 🔎 `findIndex()` – Index des ersten passenden Werts

```js
let index = zahlen.findIndex(n => n > 100);
console.log(index); // 3 (Index von 130)
```

---

## 🔘 `some()` – Prüfen, ob mindestens 1 Element passt

```js
let ergebnisse = [1, 3, 7, 10];

ergebnisse.some(x => x > 8); // true
```

---

## 🔗 `every()` – Prüfen, ob alle Elemente passen

```js
ergebnisse.every(x => x < 20); // true
ergebnisse.every(x => x > 5);  // false
```

---

## 🧪 Kombiniert verwenden

```js
const personen = [
  { name: "Anna", alter: 25 },
  { name: "Ben", alter: 32 },
  { name: "Clara", alter: 19 }
];

personen.find(p => p.alter < 30);       // { name: "Anna", alter: 25 }
personen.some(p => p.name === "Ben");   // true
personen.every(p => p.alter > 18);      // true
```

---

## 🧠 Zusammenfassung

| Methode        | Ziel                            | Rückgabewert       |
|----------------|----------------------------------|---------------------|
| `indexOf()`    | Index eines Werts                | `0`, `1`, ..., `-1` |
| `includes()`   | Existiert der Wert?              | `true` / `false`    |
| `find()`       | Erstes Element nach Bedingung    | Element / `undefined` |
| `findIndex()`  | Index des ersten Treffers        | Index / `-1`        |
| `some()`       | Mindestens ein Treffer?          | `true` / `false`    |
| `every()`      | Alle müssen Bedingung erfüllen   | `true` / `false`    |
