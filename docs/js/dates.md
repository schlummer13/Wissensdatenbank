# 🕒 Date (Datum & Zeit)

JavaScript bietet mit dem `Date`-Objekt eine eingebaute Möglichkeit, um mit Datum und Uhrzeit zu arbeiten. Es unterstützt das **Abrufen, Setzen, Formatieren und Berechnen** von Zeitwerten.

---

## 📦 Erstellen eines Date-Objekts

```js
const jetzt = new Date(); // aktuelles Datum & Uhrzeit
const bestimmtesDatum = new Date("2025-06-08T12:00:00");
const ausWerten = new Date(2025, 5, 8, 12, 0, 0); // (Jahr, Monat, Tag, Std, Min, Sek)
```

> ⚠️ Achtung: Monate starten bei `0` (Januar), also ist `5` der Juni!

---

## 📆 Datum abrufen (Getter)

```js
const datum = new Date("2025-06-08T12:34:56");

datum.getFullYear();   // 2025
datum.getMonth();      // 5 (Juni)
datum.getDate();       // 8
datum.getDay();        // 0 = Sonntag, 1 = Montag, ...
datum.getHours();      // 12
datum.getMinutes();    // 34
datum.getSeconds();    // 56
datum.getMilliseconds(); // 0
datum.getTime();       // Millisekunden seit 01.01.1970 (Unix-Zeit)
```

---

## 🧩 Datum setzen (Setter)

```js
datum.setFullYear(2030);
datum.setMonth(0);       // Januar
datum.setDate(1);        // 1. Tag im Monat
datum.setHours(14);
datum.setMinutes(0);
```

---

## 🌍 Zeit mit Zeitzonen

```js
datum.toString();         // lokale Darstellung
datum.toUTCString();      // UTC Zeit
datum.toISOString();      // 2025-06-08T10:34:56.000Z
datum.toLocaleString();   // lokal angepasst
datum.toLocaleDateString(); // nur Datum
datum.toLocaleTimeString(); // nur Uhrzeit
```

> Du kannst `toLocale...` Methoden mit Optionen anpassen:

```js
datum.toLocaleString("de-DE", {
  weekday: "long",
  year: "numeric",
  month: "long",
  day: "numeric"
});
// → Sonntag, 8. Juni 2025
```

---

## 🧪 Vergleich von Daten

```js
const a = new Date("2025-01-01");
const b = new Date("2025-06-01");

a < b; // true
a.getTime() === b.getTime(); // false
```

---

## 🧮 Zeitdifferenz berechnen

```js
const start = new Date("2025-01-01");
const ende = new Date("2025-06-01");

const differenzMS = ende - start;           // in Millisekunden
const tage = differenzMS / (1000 * 60 * 60 * 24); // in Tagen
console.log(tage); // ≈ 151 Tage
```

---

## 🧰 Zeit-Utilities

| Methode                  | Beschreibung                      |
|--------------------------|-----------------------------------|
| `Date.now()`             | aktuelle Zeit in ms (seit 1970)   |
| `new Date().getTime()`   | wie `Date.now()`                  |
| `Date.parse(string)`     | Zeitwert aus String (in ms)       |
| `isNaN(new Date(...))`   | Prüfen, ob gültiges Datum         |

---

## 📆 Mini-Beispiel: Aktuelles Datum formatieren

```js
const heute = new Date();

const tag = heute.getDate().toString().padStart(2, "0");
const monat = (heute.getMonth() + 1).toString().padStart(2, "0");
const jahr = heute.getFullYear();

console.log(`${tag}.${monat}.${jahr}`); // z. B. 08.06.2025
```

---

## 📦 Alternative Libs (für komplexere Fälle)

- **Luxon** (moderne Zeitzonen & Formate)
- **date-fns** (leichtgewichtig, modulare Funktionen)
- **Day.js** (kompakt, ähnlich wie Moment.js)
- ⚠️ **Moment.js** wird nicht mehr empfohlen (veraltet, groß)

---

## 🧠 Zusammenfassung

| Thema          | Methoden (Beispiele)                  |
|----------------|----------------------------------------|
| Aktuelles Datum | `new Date()`                         |
| Teile abfragen  | `getFullYear()`, `getMonth()`, `getDate()` |
| Teile setzen    | `setHours()`, `setFullYear()`        |
| Vergleich       | `<`, `>`, `getTime()`                |
| Formatieren     | `toLocaleDateString()`, `toISOString()` |
| Berechnen       | Differenz mit `-`, dann umrechnen    |

