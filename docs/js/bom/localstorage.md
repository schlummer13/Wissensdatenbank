# 🗃️ BOM – Local Storage

## 🧩 Was ist Local Storage?

`localStorage` ist eine moderne, einfache Möglichkeit, um **Daten dauerhaft im Browser zu speichern** – **ohne Cookies**.  
Die Daten bleiben auch nach einem **Browser-Neustart** erhalten und sind **domainbasiert**.

> 📦 Key-Value-Speicher (alles als String)

---

## ✅ Vorteile von `localStorage`

- Kein Ablaufdatum
- Bis zu **5–10 MB** Speicher (je nach Browser)
- Sehr einfach zu bedienen
- Funktioniert ohne Server
- Ideal für Einstellungen, Zustände, Caching

---

## 📚 Grundfunktionen

| Methode                          | Beschreibung                                |
|----------------------------------|---------------------------------------------|
| `localStorage.setItem(key, value)` | Speichert einen Wert                       |
| `localStorage.getItem(key)`       | Holt den gespeicherten Wert                |
| `localStorage.removeItem(key)`    | Löscht einen bestimmten Eintrag            |
| `localStorage.clear()`            | Löscht **alle** Einträge                   |
| `localStorage.length`             | Anzahl gespeicherter Einträge              |
| `localStorage.key(index)`         | Key anhand Index abrufen                   |

---

## 🧪 Beispiel: Speichern & Abrufen

```js
// Speichern
localStorage.setItem("name", "Florian");

// Auslesen
let username = localStorage.getItem("name");
console.log("Hallo " + username); // Hallo Florian

// Löschen
localStorage.removeItem("name");
```

---

## 🧵 JSON-Daten speichern

`localStorage` speichert nur **Strings** – daher muss man Objekte konvertieren:

```js
const einstellungen = {
  darkmode: true,
  sprache: "de",
};

localStorage.setItem("prefs", JSON.stringify(einstellungen));

// Auslesen:
const geladen = JSON.parse(localStorage.getItem("prefs"));
console.log(geladen.sprache); // "de"
```

---

## 🛑 Einschränkungen

- Nur **Strings** möglich (→ JSON nutzen!)
- **Domain- & protocol-gebunden** (kein Zugriff über andere Seiten)
- Kein automatisches Ablaufdatum → man muss selbst aufräumen
- Nicht für **sicherheitsrelevante Daten**

---

## 🧠 Typische Anwendungsfälle

- User-Einstellungen (Theme, Sprache)
- Fortschritt in Formularen oder Quiz
- Kleine Offline-Datenbank
- Feature-Flags oder Zustände zwischenspeichern

---

## ✅ Zusammenfassung

| Aufgabe                  | Methode                              |
|--------------------------|---------------------------------------|
| Daten speichern          | `setItem("key", "value")`             |
| Daten abrufen            | `getItem("key")`                      |
| Eintrag löschen          | `removeItem("key")`                   |
| Alles löschen            | `clear()`                             |
| Objekt speichern         | `JSON.stringify(...)` + `setItem()`   |
| Objekt laden             | `JSON.parse(...)` + `getItem()`       |

