# 📚 Arrays

**Arrays** sind geordnete Listen in JavaScript. Sie erlauben es dir, mehrere Werte in einer einzigen Variablen zu speichern – z. B. Namen, Zahlen, Objekte oder gemischte Datentypen.

---

## 📌 Was ist ein Array?

Ein Array ist ein **Container für Werte** in einer festgelegten Reihenfolge:

```js
const farben = ["rot", "grün", "blau"];
```

➡️ Jeder Eintrag hat einen **Index**, beginnend bei `0`.

---

## 🔢 Zugriff auf Elemente

```js
console.log(farben[0]); // "rot"
console.log(farben[2]); // "blau"
```

---

## ✏️ Elemente ändern

```js
farben[1] = "gelb";
console.log(farben); // ["rot", "gelb", "blau"]
```

---

## ➕ Neue Elemente hinzufügen

```js
farben.push("lila");     // ans Ende
farben.unshift("pink");  // an den Anfang
```

---

## ❌ Elemente entfernen

```js
farben.pop();    // entfernt letztes Element
farben.shift();  // entfernt erstes Element
```

---

## 🧱 Array erstellen

```js
const leer = [];
const zahlen = [1, 2, 3, 4];
const gemischt = ["Text", 42, true];
```

---

## 🔁 Über ein Array iterieren

```js
for (let i = 0; i < farben.length; i++) {
  console.log(farben[i]);
}

// Oder:
farben.forEach(farbe => console.log(farbe));
```

---

## 🔧 Nützliche Array-Methoden

| Methode         | Beschreibung                            |
|------------------|------------------------------------------|
| `push()`        | ans Ende anhängen                        |
| `pop()`         | letztes Element entfernen                |
| `unshift()`     | an Anfang einfügen                       |
| `shift()`       | erstes Element entfernen                 |
| `length`        | Anzahl der Elemente                      |
| `includes()`    | prüft, ob ein Wert enthalten ist         |
| `indexOf()`     | Position eines Elements (oder -1)        |
| `slice()`       | Teilarray erzeugen                       |
| `splice()`      | Elemente entfernen/ersetzen              |
| `join()`        | Array zu String verbinden                |
| `reverse()`     | Reihenfolge umdrehen                     |
| `sort()`        | sortieren (Standard: alphabetisch)       |

---

## 🧪 Beispiel: `splice()` & `slice()`

```js
const zahlen = [1, 2, 3, 4, 5];

let teil = zahlen.slice(1, 3);  // [2, 3] – Original bleibt
zahlen.splice(2, 1);           // entfernt 1 Element ab Index 2
```

---

## 🔍 Suche & Prüfung

```js
zahlen.includes(3);   // true
zahlen.indexOf(4);    // z. B. 2
```

---

## 🎯 Mapping & Filtern

```js
const quadrate = zahlen.map(n => n * n);
const gerade = zahlen.filter(n => n % 2 === 0);
```

---

## 🎛️ Transformation

```js
const namen = ["Max", "Anna", "Luca"];
console.log(namen.join(", ")); // "Max, Anna, Luca"
```

---

## 🧠 Mehrdimensionale Arrays (Arrays in Arrays)

```js
const matrix = [
  [1, 2],
  [3, 4]
];

console.log(matrix[0][1]); // 2
```

---

## 🧾 Array vs. Objekt

| Typ    | Verwendung                           |
|--------|--------------------------------------|
| Array  | geordnete Liste (Index)              |
| Objekt | benannte Daten (Key:Value)           |

---

## ✅ Tipps

- Arrays sind **veränderlich** (mutable)
- Zugriff auf nicht vorhandene Indizes gibt `undefined`
- Nutze `const` für Arrays, wenn sie nicht neu zugewiesen werden sollen

---

## 📚 Beispiele

```js
const todos = [];

function addTodo(text) {
  todos.push(text);
}

function zeigeTodos() {
  todos.forEach((t, i) => console.log(`${i + 1}: ${t}`));
}

addTodo("Einkaufen");
addTodo("Üben");
zeigeTodos();
// 1: Einkaufen
// 2: Üben
```