# 🛠️ Array-Methoden

Arrays in JavaScript bieten eine riesige Sammlung an Methoden, um Daten **einfach zu verändern, zu filtern, zu sortieren oder zu durchlaufen**. Hier findest du die wichtigsten Methoden mit Erklärung und Beispielen.

---

## 📋 Übersicht

| Kategorie         | Methoden-Beispiele                            |
|------------------|------------------------------------------------|
| Hinzufügen/Entfernen | `push()`, `pop()`, `shift()`, `unshift()`, `splice()` |
| Durchlaufen       | `forEach()`, `map()`                          |
| Suchen & Prüfen   | `includes()`, `indexOf()`, `find()`, `some()`, `every()` |
| Filtern & Transformieren | `filter()`, `map()`, `reduce()`         |
| Sortieren         | `sort()`, `reverse()`                         |
| Kombinieren       | `concat()`, `join()`, `flat()`                |
| Kopieren/Teilen   | `slice()`, `splice()`, `toSorted()`, `toReversed()` |

---

## ➕ Hinzufügen & Entfernen

### `push()` – ans Ende anhängen

```js
let farben = ["rot", "blau"];
farben.push("grün"); // ["rot", "blau", "grün"]
```

### `pop()` – letztes Element entfernen

```js
farben.pop(); // ["rot", "blau"]
```

### `unshift()` – an den Anfang einfügen

```js
farben.unshift("gelb"); // ["gelb", "rot", "blau"]
```

### `shift()` – erstes Element entfernen

```js
farben.shift(); // ["rot", "blau"]
```

### `splice()` – Elemente löschen, ersetzen oder einfügen

```js
let zahlen = [1, 2, 3, 4];
zahlen.splice(1, 2); // entfernt ab Index 1, 2 Elemente → [1, 4]
```

---

## 🔁 Durchlaufen

### `forEach()` – führt Funktion für jedes Element aus

```js
let namen = ["Anna", "Ben"];
namen.forEach(name => console.log("Hallo " + name));
```

### `map()` – neues Array mit verändertem Inhalt

```js
let zahlen = [1, 2, 3];
let quadrate = zahlen.map(x => x * x); // [1, 4, 9]
```

---

## 🔍 Suchen & Prüfen

### `includes()` – prüft ob Wert enthalten ist

```js
let obst = ["Apfel", "Banane"];
obst.includes("Banane"); // true
```

### `indexOf()` – Position eines Elements

```js
obst.indexOf("Apfel"); // 0
```

### `find()` – erstes Element, das Bedingung erfüllt

```js
let zahlen = [1, 5, 10];
let ersteGroessere5 = zahlen.find(n => n > 5); // 10
```

### `some()` – prüft ob **mindestens ein** Element passt

```js
zahlen.some(n => n < 0); // false
```

### `every()` – prüft ob **alle** Elemente passen

```js
zahlen.every(n => n > 0); // true
```

---

## 🎯 Filtern & Reduzieren

### `filter()` – erstellt neues Array mit passenden Werten

```js
let noten = [1, 2, 3, 4, 5];
let guteNoten = noten.filter(n => n <= 3); // [1, 2, 3]
```

### `reduce()` – auf einen Wert „reduzieren“

```js
let summe = [1, 2, 3].reduce((acc, val) => acc + val, 0); // 6
```

---

## 🔀 Sortieren

### `sort()` – alphabetisch oder benutzerdefiniert

```js
[3, 1, 10].sort(); // [1, 10, 3] → Achtung: als Strings!
[3, 1, 10].sort((a, b) => a - b); // [1, 3, 10]
```

### `reverse()` – Reihenfolge umkehren

```js
[1, 2, 3].reverse(); // [3, 2, 1]
```

---

## 🧩 Kombinieren & Trennen

### `concat()` – Arrays zusammenführen

```js
[1, 2].concat([3, 4]); // [1, 2, 3, 4]
```

### `join()` – Array zu String verbinden

```js
["Hallo", "Welt"].join(" "); // "Hallo Welt"
```

### `flat()` – verschachtelte Arrays „glätten“

```js
[1, [2, [3]]].flat(2); // [1, 2, 3]
```

---

## ✂️ Kopieren & Ausschneiden

### `slice()` – Teilarray kopieren

```js
let zahlen = [0, 1, 2, 3];
zahlen.slice(1, 3); // [1, 2]
```

### `toReversed()` / `toSorted()` (ab ES2023)

```js
[1, 2, 3].toReversed(); // [3, 2, 1]
[3, 1, 2].toSorted();   // [1, 2, 3]
```

---

## 🧠 Weitere Tricks

- `Array.isArray(variable)` → Prüft, ob es sich um ein Array handelt
- `new Array(5).fill(0)` → Erstellt Array mit 5 Nullen
- `[...array]` → Kopie des Arrays

---

## ✅ Zusammenfassung

| Methode        | Zweck                              |
|----------------|-------------------------------------|
| `push/pop`     | Ende bearbeiten                     |
| `shift/unshift`| Anfang bearbeiten                   |
| `map/filter`   | transformieren und filtern          |
| `reduce`       | zusammenrechnen                     |
| `find/some`    | prüfen/suchen                       |
| `sort/slice`   | sortieren oder ausschneiden         |
| `forEach`      | durchlaufen                         |

