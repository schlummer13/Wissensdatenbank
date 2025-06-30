# 🔒 `const` bei Arrays

In JavaScript wird `const` verwendet, um eine **Konstante Variable** zu deklarieren. Das bedeutet: **Die Referenz kann nicht neu zugewiesen werden** – der Inhalt eines Arrays kann aber sehr wohl **verändert** werden!

---

## 📌 Grundregel

```js
const zahlen = [1, 2, 3];

// ✅ Inhalt darf verändert werden
zahlen.push(4); // → [1, 2, 3, 4]

// ❌ Aber nicht neu zugewiesen!
zahlen = [9, 8]; // ❌ TypeError
```

> `const` verhindert das **Ersetzen der Referenz**, nicht die **Veränderung der Daten**.

---

## 🧠 Warum `const` bei Arrays sinnvoll ist

- Schützt vor versehentlichem **Überschreiben der Variable**
- Macht den Code **vorhersehbarer** und **lesbarer**
- Besonders praktisch bei Arrays, die **mutiert**, aber nicht ersetzt werden sollen

---

## ✅ Erlaubte Operationen mit `const` Arrays

```js
const farben = ["rot", "blau"];

// Elemente hinzufügen
farben.push("grün");   // ["rot", "blau", "grün"]

// Elemente entfernen
farben.pop();          // ["rot", "blau"]

// Elemente ändern
farben[0] = "gelb";    // ["gelb", "blau"]
```

---

## ❌ Nicht erlaubt

```js
const farben = ["rot", "blau"];

// ❌ Neue Referenz zuweisen
farben = ["grün", "schwarz"]; // Fehler!
```

---

## 🧪 Beispiel: mutable vs immutable

```js
const liste = [1, 2, 3];

// Direkt verändern (mutable)
liste.push(4);       // ✅

// Neue Kopie erzeugen (immutable)
const neueListe = [...liste, 5]; // ✅, neue Referenz
```

---

## 📚 Vergleich: `let` vs. `const` vs. `var`

| Deklaration | Wiederzuweisbar | Veränderbar (z. B. Array-Push) | Blockscope |
|-------------|------------------|-------------------------------|------------|
| `const`     | ❌ Nein          | ✅ Ja                         | ✅ Ja      |
| `let`       | ✅ Ja            | ✅ Ja                         | ✅ Ja      |
| `var`       | ✅ Ja            | ✅ Ja                         | ❌ Nein    |

---

## ✅ Fazit

- Verwende `const` für Arrays, **wenn du die Referenz nicht ändern willst**
- Es bleibt möglich, den Inhalt (Elemente) zu verändern
- Für **unveränderliche Datenstrukturen** nutzt du z. B. `Object.freeze()` oder Libraries wie **Immer.js**
