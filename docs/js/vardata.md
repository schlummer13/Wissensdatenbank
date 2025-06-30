# 🧮 Variablen & Datentypen

In JavaScript dienen **Variablen** dazu, Daten zu speichern und im Code wiederzuverwenden. Sie sind flexibel, dynamisch typisiert und ein zentrales Werkzeug beim Programmieren.

---

## 📝 Was ist eine Variable?

Eine Variable ist ein **benannter Speicherplatz**, der einen **Wert** enthält.  
Der Wert kann sich im Laufe des Programms ändern (mutable) – je nach Deklarationsart.

---

## 📌 Variablen deklarieren

### 🔹 `var`

```js
var x = 5;
```

- Älterer Standard (seit 1995)
- **Funktionaler Gültigkeitsbereich**
- Wird **gehoisted** (nach oben gezogen)
- Wird heute **selten empfohlen**

---

### 🔹 `let`

```js
let name = "Anna";
```

- **Blockscoped** (z. B. `{ ... }`)
- Wert kann geändert werden
- **Empfohlene Standardvariante**

---

### 🔹 `const`

```js
const PI = 3.14;
```

- **Blockscoped**
- **Nicht neu zuweisbar** (konstant)
- Achtung: Objekte und Arrays bleiben veränderbar!

```js
const arr = [1, 2];
arr.push(3); // Erlaubt!
```

---

## 🧠 Dynamische Typisierung

JavaScript ist **nicht typensicher** – der Typ ergibt sich aus dem gespeicherten Wert:

```js
let x = 5;        // Zahl
x = "Hallo";      // jetzt: String
```

---

## 🔠 Primitive Datentypen

| Typ         | Beispiel                     | Beschreibung                              |
|-------------|------------------------------|--------------------------------------------|
| `string`    | `"Hallo"`, `'Test'`          | Textinhalt                                 |
| `number`    | `42`, `3.14`, `-7`            | Ganzzahlen & Fließkommazahlen              |
| `boolean`   | `true`, `false`              | Logische Werte                             |
| `undefined` | `let a;` → `a === undefined` | Variable deklariert, aber kein Wert        |
| `null`      | `let b = null`               | Absichtliche Leere                         |
| `bigint`    | `123n`                       | Für große Ganzzahlen                       |
| `symbol`    | `Symbol("id")`               | Einzigartige, unveränderliche Kennung      |

---

## 📦 Strukturelle Datentypen (Referenztypen)

| Typ       | Beispiel                         | Beschreibung                        |
|-----------|----------------------------------|-------------------------------------|
| `object`  | `{ name: "Anna", age: 30 }`      | Schlüssel-Wert-Paare                |
| `array`   | `[1, 2, 3]`                      | Auflistung von Werten               |
| `function`| `function greet() {}`            | Funktionen sind auch Objekte        |
| `date`    | `new Date()`                     | Zeit- und Datumsobjekte             |
| `regexp`  | `/abc/i`                         | Reguläre Ausdrücke                  |
| `map`     | `new Map()`                      | Schlüssel-Wert-Kollektion (beliebige Schlüssel) |
| `set`     | `new Set()`                      | Einfache Liste ohne Duplikate       |

---

## 🔍 Typen prüfen

```js
typeof "Hallo"    // "string"
typeof 42         // "number"
typeof true       // "boolean"
typeof undefined  // "undefined"
typeof null       // "object" ← historischer Bug
typeof {}         // "object"
typeof []         // "object"
typeof function() {} // "function"
```

Für Arrays und `null` besser:

```js
Array.isArray([]);    // true
value === null;       // true
```

---

## 🎯 Typumwandlung (Casting)

### 🔸 Explizit

```js
Number("5");       // 5
String(123);       // "123"
Boolean(0);        // false
```

### 🔸 Implizit

```js
"5" + 2;           // "52" (String)
"5" - 2;           // 3 (Number)
true + false;      // 1
```

---

## 🔐 `const`, `let`, `var` im Vergleich

| Eigenschaft       | `var`         | `let`         | `const`       |
|-------------------|---------------|---------------|----------------|
| Gültigkeitsbereich| Funktion      | Block         | Block          |
| Neuzuweisung      | ✔             | ✔             | ❌             |
| Wiederdeklaration | ✔             | ❌             | ❌             |
| Hoisting          | ✔ (initial `undefined`) | ✔ (kein Zugriff vorher) | ✔ (kein Zugriff vorher) |

---

## 📚 Beispiel

```js
let vorname = "Lisa";
const alter = 28;
var status = "aktiv";

console.log(`${vorname} ist ${alter} Jahre alt.`); // Lisa ist 28 Jahre alt
```

---

## 🧪 Teste dich selbst

1. Was ist der Unterschied zwischen `null` und `undefined`?
2. Wann verwendet man `const`, wann `let`?
3. Was gibt `typeof null` zurück?
