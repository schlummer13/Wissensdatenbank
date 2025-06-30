# 🔁 `for`-Schleifen komplett erklärt

Mit `for`-Schleifen kannst du **Wiederholungen** (Loops) im Code umsetzen. Sie helfen dabei, Aufgaben **mehrfach automatisch auszuführen**, z. B. durch Arrays zu gehen oder Zahlen hochzuzählen.

---

## 🧩 Klassische `for`-Schleife

Die bekannteste Form:

```js
for (let i = 0; i < 5; i++) {
  console.log("Zahl:", i);
}
```

### Erklärung:

| Teil         | Funktion                                  |
|--------------|-------------------------------------------|
| `let i = 0`  | Startwert                                 |
| `i < 5`      | Schleife läuft, solange Bedingung wahr    |
| `i++`        | Erhöht Zähler bei jedem Durchlauf         |

➡️ Gibt aus: `0`, `1`, `2`, `3`, `4`

---

## 🔄 `for...of` – Für Arrays und Iterables

```js
const namen = ["Anna", "Ben", "Clara"];

for (const name of namen) {
  console.log(name);
}
```

- Geht automatisch **Element für Element** durch das Array
- Funktioniert auch mit:
  - **Strings**
  - **Sets**
  - **Maps**
  - **NodeLists**
  - **DOM-Kollektionen**

---

## 🔄 `for...in` – Für Objekte (und Arrays mit Index)

```js
const person = {
  name: "Max",
  alter: 30
};

for (const key in person) {
  console.log(key + ": " + person[key]);
}
```

➡️ Gibt die **Schlüssel (Keys)** aus – ideal für Objekte.

⚠️ Nicht empfohlen für Arrays – verwende stattdessen `for` oder `for...of`.

---

## 🧠 `for...of` vs. `for...in`

| Zweck       | `for...in`             | `for...of`                     |
|-------------|------------------------|--------------------------------|
| Objekte     | ✅ Ja                   | ❌ Nein                        |
| Arrays      | ⚠️ Ja (gibt Index)     | ✅ Ja (gibt Wert)              |
| Strings     | ❌ Nein                | ✅ Ja                          |
| Ergebnis    | Schlüssel (Key)        | Wert                           |

---

## 📚 Weitere Varianten

### 🔁 Rückwärts zählen

```js
for (let i = 10; i >= 0; i--) {
  console.log(i);
}
```

➡️ Zählt von 10 bis 0 runter

---

### 🔁 Mehrere Variablen in Schleife

```js
for (let i = 0, j = 10; i < j; i++, j--) {
  console.log(i, j);
}
```

➡️ Zwei Zähler gleichzeitig – z. B. von außen nach innen iterieren

---

## ⏭️ `break`, `continue`, `return`

### 🔨 `break` – Schleife vorzeitig beenden

```js
for (let i = 0; i < 10; i++) {
  if (i === 5) break;
  console.log(i); // Nur bis 4
}
```

### ⏭️ `continue` – Durchlauf überspringen

```js
for (let i = 0; i < 5; i++) {
  if (i === 2) continue;
  console.log(i); // Gibt 0, 1, 3, 4 aus
}
```

### 🔙 `return` – Funktion beenden (nicht nur Schleife!)

```js
function findeErsteZahl(arr) {
  for (let zahl of arr) {
    if (zahl > 10) return zahl; // Beendet Funktion
  }
  return null;
}
```

> ⚠️ `return` funktioniert **nur innerhalb von Funktionen**.

---

## 🧶 Was ist iterierbar (iterable)?

Ein **Iterable** ist ein Objekt, das mit einer Schleife wie `for...of` durchlaufen werden kann.  
Dazu gehören:

- **Array**
- **String**
- **Set**
- **Map**
- **NodeList** (z. B. `document.querySelectorAll`)
- Eigene Iterables mit `Symbol.iterator`

Beispiel mit einem String:

```js
for (let buchstabe of "Hallo") {
  console.log(buchstabe);
}
```

➡️ Gibt aus: `H`, `a`, `l`, `l`, `o`

---

## 🔁 Array mit Index & Wert

```js
const zahlen = [10, 20, 30];

for (let i = 0; i < zahlen.length; i++) {
  console.log(`Index ${i}: ${zahlen[i]}`);
}
```

Oder eleganter mit `forEach()`:

```js
zahlen.forEach((wert, index) => {
  console.log(`Index ${index}: ${wert}`);
});
```

---

## 🧪 Beispiel: Array summieren mit `for...of`

```js
const werte = [5, 8, 3];
let summe = 0;

for (const wert of werte) {
  summe += wert;
}

console.log("Gesamtsumme:", summe); // 16
```

---

## ✅ Zusammenfassung

| Schleife      | Wann verwenden?                                    |
|---------------|----------------------------------------------------|
| `for`         | Klassisch – mit Startwert, Bedingung und Zähler    |
| `for...of`    | Für alle **iterierbaren** Objekte                  |
| `for...in`    | Für **Objektschlüssel**                            |
| `forEach()`   | Für Arrays – mit Callback (nicht abbrechbar)       |
| `break`       | Schleife sofort beenden                            |
| `continue`    | Nächster Durchlauf, ohne Rest des Codes            |
| `return`      | Funktion verlassen (innerhalb von Schleifen)       |

---

Mit diesen Varianten kannst du **jede Art von wiederholender Logik flexibel abbilden** – von simplen Schleifen bis zu dynamischen Array-Verarbeitungssystemen.