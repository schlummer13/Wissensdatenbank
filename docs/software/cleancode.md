# 🧼 Clean Code – Sauber programmieren

**Clean Code** bedeutet: **klarer, verständlicher, wartbarer und zuverlässiger Code**. Es ist kein eigener Code-Stil, sondern ein **Konzept** guter Softwareentwicklung.

Der Begriff wurde besonders durch das Buch *Clean Code* von **Robert C. Martin (Uncle Bob)** bekannt.

---

## 🎯 Ziel von Clean Code

| Ziel                  | Warum es wichtig ist                         |
|------------------------|----------------------------------------------|
| Lesbarkeit             | Andere (oder du selbst) verstehen den Code später schneller |
| Wartbarkeit            | Code lässt sich leichter anpassen oder erweitern |
| Testbarkeit            | Sauberer Code ist einfacher zu testen        |
| Fehlervermeidung       | Klare Strukturen verhindern Bugs             |
| Teamfähigkeit          | Gemeinsames Arbeiten wird produktiver        |

---

## 🧠 Grundprinzipien

### 1. **Sag, was du meinst** – gute Namen

✅ **Gute Namen sagen aus, was etwas macht oder enthält**:

```js
// ❌ Schlecht
let x = 3;

// ✅ Besser
let anzahlArtikelImWarenkorb = 3;
```

Regeln:

- Variablennamen sind **aussagekräftig**
- Keine Abkürzungen wie `btn1`, `x`, `tmp`
- Funktionen mit **Verb**: `berechneSumme()`, `ladeBenutzer()`

---

### 2. **Eine Funktion = eine Aufgabe**

Jede Funktion soll **nur EINE Sache tun**:

```js
// ❌ Schlecht: tut mehrere Dinge
function bestellungAbschicken() {
  datenValidieren();
  datenSpeichern();
  emailSenden();
}

// ✅ Besser: klar getrennt
function validiereBestellung() {}
function speichereBestellung() {}
function sendeBestaetigung() {}
```

---

### 3. **Saubere Struktur & Einrückung**

Code sollte wie ein gut strukturiertes Dokument aussehen:

```js
function pruefeAlter(alter) {
  if (alter >= 18) {
    return "Erwachsen";
  } else {
    return "Minderjährig";
  }
}
```

➡️ Einheitlicher Stil macht Code **lesbar wie Text**.

---

### 4. **Vermeide magische Zahlen & Strings**

✅ Keine „geheimen“ Werte mitten im Code:

```js
// ❌
if (wert > 42) { ... }

// ✅
const HOECHSTWERT = 42;
if (wert > HOECHSTWERT) { ... }
```

---

### 5. **Kommentare nur wenn nötig**

- Besser: **sprechender Code**
- Kommentare nicht zur Entschuldigung von schlechtem Code
- Gute Kommentare erklären das *Warum*, nicht das *Wie*

```js
// ❌ Schlecht
// Prüfe, ob Benutzer eingeloggt ist
if (user.loggedIn === true) { ... }

// ✅ Besser
if (user.istEingeloggt()) { ... }
```

---

### 6. **Kurze Funktionen**

- Ideal: **5–20 Zeilen**
- Jede Funktion sollte **kontextunabhängig testbar** sein

---

### 7. **Fehlerbehandlung nicht ignorieren**

```js
// ❌ Schlecht
try {
  ladeDaten();
} catch (e) {
  // nichts
}

// ✅ Besser
try {
  ladeDaten();
} catch (e) {
  console.error("Fehler beim Laden der Daten:", e.message);
}
```

---

## 🛠 Best Practices

| Regel                           | Warum wichtig?                           |
|----------------------------------|-------------------------------------------|
| Schreibe erst funktionierenden Code, dann refactor | Qualität Schritt für Schritt verbessern |
| Schreibe Tests                  | Tests zeigen Bugs und helfen beim Refactoring |
| DRY – Don't Repeat Yourself     | Vermeide Dopplungen – nutze Funktionen    |
| KISS – Keep It Simple, Stupid   | Einfach ist besser als clever             |
| YAGNI – You Ain’t Gonna Need It | Bau nur, was wirklich gebraucht wird      |

---

## 🔁 Refactoring-Beispiel

**Vorher:**

```js
if (user.age > 18) {
  console.log("Darf teilnehmen");
} else {
  console.log("Darf nicht teilnehmen");
}
```

**Nachher (sauberer, testbarer):**

```js
function istErwachsen(user) {
  return user.age >= 18;
}

if (istErwachsen(user)) {
  console.log("Darf teilnehmen");
} else {
  console.log("Darf nicht teilnehmen");
}
```

---

## ✅ Clean Code Checkliste

- [ ] Haben Variablen & Funktionen gute Namen?
- [ ] Macht jede Funktion nur EINE Sache?
- [ ] Ist der Code lesbar & gut eingerückt?
- [ ] Gibt es duplizierten Code?
- [ ] Ist unnötiger Code gelöscht?
- [ ] Ist die Fehlerbehandlung vorhanden und sinnvoll?
- [ ] Werden magische Werte vermieden?