# 🧠 `if`, `else if`, `else`

Mit `if`-Anweisungen kannst du in JavaScript **Entscheidungen treffen**. Sie führen Code nur dann aus, wenn eine bestimmte **Bedingung erfüllt** ist.

---

## 🧩 Grundstruktur

```js
if (Bedingung) {
  // Dieser Block wird ausgeführt, wenn die Bedingung wahr ist
} else if (zweiteBedingung) {
  // Wird geprüft, wenn die erste Bedingung falsch war
} else {
  // Fängt alles andere ab
}
```

---

## ✅ Einfaches Beispiel

```js
let punkte = 85;

if (punkte >= 90) {
  console.log("Note: Sehr gut");
} else if (punkte >= 75) {
  console.log("Note: Gut");
} else if (punkte >= 60) {
  console.log("Note: Befriedigend");
} else {
  console.log("Note: Nicht bestanden");
}
```

---

## 🔍 Bedingungen in JavaScript

Bedingungen sind **Ausdrücke**, die entweder `true` oder `false` ergeben.

Beispiele:

```js
x > 10
name === "Florian"
alter <= 18
preis !== 0
```

Du kannst auch **logische Operatoren** verwenden:

```js
if (alter >= 18 && land === "DE") { ... }
if (punkte > 70 || bonus === true) { ... }
```

---

## 🚫 Was passiert bei `false`?

```js
if (false) {
  console.log("Dies wird NICHT ausgeführt");
} else {
  console.log("Das schon!");
}
```

---

## 🧠 Tipps

- **Nur eine Bedingung trifft zu** – sobald eine `true` ist, wird der Rest **übersprungen**.
- Bedingungen können beliebig **verschachtelt** werden.
- Werte wie `0`, `""`, `null`, `undefined`, `NaN`, `false` gelten als **falsy**.

---

## 🧪 Mini-Beispiele

### Altersprüfung:

```js
let alter = 20;

if (alter < 18) {
  console.log("Minderjährig");
} else {
  console.log("Volljährig");
}
```

### Benutzerrolle:

```js
let rolle = "admin";

if (rolle === "admin") {
  console.log("Zugriff erlaubt");
} else if (rolle === "editor") {
  console.log("Bearbeitung erlaubt");
} else {
  console.log("Nur Leserechte");
}
```

---

## 📦 Optional: Kurzform mit ternärem Operator

```js
let status = (punkte >= 50) ? "Bestanden" : "Nicht bestanden";
```

---

## ✅ Zusammenfassung

| Schlüsselwort | Funktion                                  |
|---------------|--------------------------------------------|
| `if`          | Führt Code aus, wenn Bedingung wahr ist    |
| `else if`     | Weitere Bedingung, wenn vorherige falsch   |
| `else`        | Wird ausgeführt, wenn alle Bedingungen falsch sind |

