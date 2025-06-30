# ⚙️ Operatoren

In JavaScript helfen dir **Operatoren**, bestimmte Aktionen auszuführen – z. B. **rechnen**, **vergleichen**, **Texte verketten** oder **Bedingungen prüfen**. Sie gehören zu den absoluten Grundlagen beim Programmieren.

---

## 📦 Übersicht der Operatoren

| Kategorie            | Beschreibung                                   |
|----------------------|------------------------------------------------|
| **Arithmetisch**     | Zahlen addieren, subtrahieren, multiplizieren usw. |
| **Vergleich**        | Sind Werte gleich? Ist etwas größer oder kleiner? |
| **Logisch**          | Bedingungen miteinander verknüpfen              |
| **Zuweisung**        | Werte in Variablen speichern oder verändern     |
| **Strings**          | Texte zusammenfügen                            |
| **Typprüfung**       | Herausfinden, welcher Datentyp vorliegt        |
| **Sonstige**         | z. B. `? :` oder `delete`                      |

---

## ➕ Arithmetische Operatoren – Rechnen in JavaScript

```js
let x = 10;
let y = 3;

x + y   // 13 → Plus
x - y   // 7 → Minus
x * y   // 30 → Mal
x / y   // 3.333... → Geteilt
x % y   // 1 → Rest (Modulo)
x ** y  // 1000 → Potenz (10³)
```

---

## 🔁 Hoch- und runterzählen: Inkrement & Dekrement

```js
let i = 5;

i++;    // i wird um 1 erhöht (nachher)
++i;    // i wird sofort erhöht

i--;    // i wird um 1 verringert
--i;    // sofort verringert
```

💡 Wird oft in Schleifen verwendet!

---

## 📏 Vergleichsoperatoren – Sind Werte gleich?

| Operator | Bedeutung                 | Beispiel (`a = 5`, `b = "5"`) |
|----------|---------------------------|-------------------------------|
| `==`     | Ist gleich (nur Wert)     | `a == b` → `true`             |
| `===`    | Streng gleich (Typ & Wert)| `a === b` → `false`           |
| `!=`     | Ungleich (Wert)           | `a != b` → `false`            |
| `!==`    | Streng ungleich           | `a !== b` → `true`            |
| `>` `<`  | Größer / Kleiner          | `a > 3` → `true`              |
| `>=` `<=`| Größer-/Kleiner-gleich    | `a <= 5` → `true`             |

🧠 **Merke**: Immer `===` statt `==` verwenden, um sicherzugehen, dass auch der **Datentyp** stimmt.

---

## 🔗 Logische Operatoren – Bedingungen verbinden

```js
true && false   // false → UND (beide müssen stimmen)
true || false   // true  → ODER (eine reicht)
!true           // false → NICHT (umkehren)
```

| Symbol | Name       | Erklärung                          |
|--------|------------|------------------------------------|
| `&&`   | UND         | Nur `true`, wenn beide stimmen    |
| `||`   | ODER        | `true`, wenn mind. eine stimmt    |
| `!`    | NICHT       | Wandelt `true` in `false` um      |

---

## 🧮 Zuweisungsoperatoren – Variablen verändern

```js
let a = 10;

a += 5;  // a = a + 5 → 15
a -= 3;  // a = a - 3 → 12
a *= 2;  // a = a * 2 → 24
a /= 6;  // a = a / 6 → 4
a %= 3;  // a = a % 3 → 1
a **= 2; // a = a ** 2 → 1
```

---

## 🧵 Texte verketten (Strings)

```js
let vorname = "Max";
let nachname = "Muster";

let name = vorname + " " + nachname;
// Max Muster
```

---

## ❓ Der ternäre Operator – Kurzform für if/else

```js
let alter = 20;
let status = (alter >= 18) ? "Erwachsen" : "Kind";
```

Bedeutung:

```js
// Wenn alter ≥ 18 → "Erwachsen", sonst → "Kind"
```

---

## 🔍 Typ prüfen mit `typeof`, `instanceof`, `in`

```js
typeof 123            // "number"
typeof "Hallo"        // "string"
typeof null           // "object" (Sonderfall!)

[1, 2, 3] instanceof Array  // true

"length" in [1, 2, 3]       // true
```

---

## 📘 Weitere wichtige Operatoren

| Operator     | Bedeutung                                               |
|--------------|----------------------------------------------------------|
| `delete`     | Löscht eine Eigenschaft aus einem Objekt                |
| `typeof`     | Zeigt an, welcher Typ vorliegt (`"number"`, `"object"`, …) |
| `in`         | Prüft, ob eine Eigenschaft vorhanden ist                |
| `instanceof` | Ist ein Objekt eine Instanz eines bestimmten Typs?      |
| `??`         | Nullish Coalescing: liefert rechten Wert, wenn links `null` oder `undefined` ist |

```js
let name = null;
let username = name ?? "Gast";  // → "Gast"
```

---

## 🧪 Mini-Beispiel mit allem kombiniert

```js
let score = 85;

let note = (score >= 90) ? "Sehr gut" :
           (score >= 75) ? "Gut" :
           (score >= 60) ? "Befriedigend" :
           "Nicht bestanden";

console.log(note); // Gut
```