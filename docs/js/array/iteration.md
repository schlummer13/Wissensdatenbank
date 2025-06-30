# 🔁 Array Iteration

Die Iteration ist das **Durchlaufen** eines Arrays, um jedes Element zu verarbeiten. JavaScript bietet dafür viele Möglichkeiten – von einfachen Schleifen bis zu modernen Methoden wie `map()` oder `forEach()`.

---

## 📋 Übersicht

| Methode           | Beschreibung                                  |
|-------------------|-----------------------------------------------|
| `for`             | Klassische Zählschleife                       |
| `for...of`        | Iteration über Werte                          |
| `forEach()`       | Funktion wird pro Element ausgeführt          |
| `map()`           | Neues Array mit veränderten Werten            |
| `filter()`        | Neues Array mit passenden Werten              |
| `reduce()`        | Auf einen Wert reduzieren (z. B. Summe)       |
| `while`, `do...while` | klassische Schleifen mit Bedingung        |

---

## 🧮 `for` – Klassische Schleife

```js
const zahlen = [10, 20, 30];

for (let i = 0; i < zahlen.length; i++) {
  console.log(zahlen[i]);
}
```

---

## 🌀 `for...of` – moderne Schleife für Werte

```js
for (let zahl of zahlen) {
  console.log(zahl);
}
```

---

## 🧩 `forEach()` – Callback für jedes Element

```js
zahlen.forEach((wert, index) => {
  console.log(index + ": " + wert);
});
```

- **Verändert nichts** – dient nur zum Durchlaufen
- Kein `break`/`continue` möglich

---

## 🔁 `map()` – Werte umwandeln

```js
let doppelt = zahlen.map(n => n * 2);
console.log(doppelt); // [20, 40, 60]
```

- Gibt ein neues Array zurück
- **Unveränderlich**: Original bleibt erhalten

---

## 🔍 `filter()` – nur passende Elemente behalten

```js
let gross = zahlen.filter(n => n > 15);
console.log(gross); // [20, 30]
```

---

## 🧮 `reduce()` – alles auf einen Wert zusammenführen

```js
let summe = zahlen.reduce((acc, val) => acc + val, 0);
console.log(summe); // 60
```

---

## 🔄 `while` – wiederholen solange Bedingung erfüllt

```js
let i = 0;
while (i < zahlen.length) {
  console.log(zahlen[i]);
  i++;
}
```

---

## ⏳ `do...while` – mindestens einmal ausführen

```js
let j = 0;
do {
  console.log(zahlen[j]);
  j++;
} while (j < zahlen.length);
```

---

## 🧪 Beispiel mit `map()`, `filter()`, `reduce()`

```js
const noten = [1, 4, 2, 5, 3];

// Nur gute Noten
const gut = noten.filter(n => n <= 3);

// Alle verdoppeln
const doppelt = noten.map(n => n * 2);

// Durchschnitt berechnen
const schnitt = noten.reduce((a, b) => a + b, 0) / noten.length;
```

---

## ✅ Zusammenfassung

| Methode     | Zweck                         | Rückgabewert     |
|-------------|-------------------------------|------------------|
| `forEach()` | ausführen, kein Rückgabewert  | `undefined`      |
| `map()`     | transformieren                | neues Array      |
| `filter()`  | filtern                       | neues Array      |
| `reduce()`  | auf Wert reduzieren           | z. B. Zahl       |
| `for...of`  | einfache Schleife über Werte  | —                |

