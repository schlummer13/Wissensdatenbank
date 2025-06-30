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

| Teil            | Funktion                            |
|------------------|--------------------------------------|
| `let i = 0`      | Startwert                           |
| `i < 5`          | Schleife läuft, solange das wahr ist |
| `i++`            | Zähler wird bei jedem Durchlauf erhöht |

➡️ Gibt aus: `0`, `1`, `2`, `3`, `4`

---

## 🔄 `for...of` – für Arrays und Iterierbares

```js
const namen = ["Anna", "Ben", "Clara"];

for (const name of namen) {
  console.log(name);
}
```

- Geht automatisch **Element für Element** durch das Array
- Funktioniert auch mit **Strings**, **Sets**, **Maps**, **NodeLists**

➡️ Gibt aus: `"Anna"`, `"Ben"`, `"Clara"`

---

## 🔄 `for...in` – für Objekte (und Arrays mit Index)

```js
const person = {
  name: "Max",
  alter: 30
};

for (const eigenschaft in person) {
  console.log(eigenschaft + ": " + person[eigenschaft]);
}
```

- Gibt **Schlüssel (Keys)** aus
- Auch für Arrays nutzbar, aber **nicht empfohlen**

➡️ Gibt aus:  
`name: Max`  
`alter: 30`

---

## 🧠 Unterschied `for...of` vs `for...in`

| Zweck       | `for...in`                            | `for...of`                     |
|-------------|----------------------------------------|--------------------------------|
| Objekte     | ✅ Ja                                   | ❌ Nein                        |
| Arrays      | ⚠️ Ja (liefert Index)                  | ✅ Ja (liefert Wert)           |
| Strings     | ❌ Nein                                | ✅ Ja                          |
| Ergebnis    | **Key (String)**                      | **Wert**                      |

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

### 🔁 Mehrfachbedingungen

```js
for (let i = 0, j = 10; i < j; i++, j--) {
  console.log(i, j);
}
```

➡️ Zwei Zähler gleichzeitig

---

## ⏭️ `break` & `continue`

### `break` – Schleife abbrechen

```js
for (let i = 0; i < 10; i++) {
  if (i === 5) break;
  console.log(i); // Nur bis 4
}
```

### `continue` – aktuellen Durchlauf überspringen

```js
for (let i = 0; i < 5; i++) {
  if (i === 2) continue;
  console.log(i); // Gibt 0, 1, 3, 4 aus
}
```

---

## 🔁 Array mit Index & Wert

```js
const zahlen = [10, 20, 30];

for (let i = 0; i < zahlen.length; i++) {
  console.log(`Index ${i}: ${zahlen[i]}`);
}
```

Oder:

```js
zahlen.forEach((wert, index) => {
  console.log(`Index ${index}: ${wert}`);
});
```

---

## 🧪 Beispiel: Summe von Array-Werten

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

| Schleife     | Wann verwenden?                                |
|--------------|------------------------------------------------|
| `for`        | Klassisch – mit Start, Bedingung, Zähler       |
| `for...of`   | Durch Arrays, Strings, Iterables gehen         |
| `for...in`   | Durch Objekte (Schlüssel)                      |
| `forEach()`  | Arrays elegant durchlaufen (Callback)          |
