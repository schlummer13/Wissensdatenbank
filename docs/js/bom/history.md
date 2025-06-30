# 🕘 BOM – `history`

## 🧩 Was ist das `history`-Objekt?

Das `history`-Objekt ermöglicht dir, mit dem **Verlauf des Browsers** zu interagieren.  
Du kannst prüfen, wie viele Seiten besucht wurden, und **vorwärts oder rückwärts** im Verlauf navigieren – ähnlich wie die Zurück-/Weiter-Schaltflächen im Browser.

👉 Das ist besonders nützlich für Single Page Applications (SPAs) und Benutzerführung.

---

## ✅ Zugriff

```js
console.log(window.history);
```

oder einfach:

```js
console.log(history);
```

---

## 📚 Wichtige Methoden

| Methode                  | Beschreibung                                   |
|---------------------------|------------------------------------------------|
| `history.back()`         | Geht **eine Seite zurück** im Verlauf          |
| `history.forward()`      | Geht **eine Seite vor** im Verlauf             |
| `history.go(n)`          | Navigiert **relativ** zur aktuellen Seite      |
| `history.pushState()`    | Fügt eine neue Seite in den Verlauf ein (SPA)  |
| `history.replaceState()` | Ersetzt die aktuelle Seite im Verlauf          |
| `history.length`         | Anzahl der besuchten Seiten in dieser Session  |

---

## 🔁 Beispiele

### 🔙 Eine Seite zurück

```js
history.back(); // wie Klick auf "Zurück"-Button
```

### 🔜 Eine Seite vor

```js
history.forward(); // wie Klick auf "Vor"-Button
```

### 🔄 N Schritte vor/zurück

```js
history.go(-1); // zurück
history.go(1);  // vor
history.go(0);  // Seite neu laden
```

---

## ⚙️ pushState() & replaceState()

Diese Methoden ändern die URL **ohne die Seite neu zu laden** – nützlich für dynamische Apps.

### 🧪 Beispiel – URL ändern, ohne neu zu laden

```js
history.pushState({ name: "Florian" }, "", "/profil");
```

### Unterschiede:

| Methode            | Effekt                                         |
|--------------------|------------------------------------------------|
| `pushState()`      | Neuer Verlaufseintrag wird hinzugefügt         |
| `replaceState()`   | Aktueller Eintrag wird ersetzt (kein Zurück)   |

---

## 📣 `popstate`-Event

Wenn der Benutzer über den Zurück-/Vorwärts-Button navigiert:

```js
window.addEventListener("popstate", (event) => {
  console.log("Verlauf geändert", event.state);
});
```

---

## ⚠️ Sicherheit & Einschränkungen

- Kein Zugriff auf den kompletten Verlauf (z. B. URLs auslesen)
- Funktioniert nur **innerhalb derselben Domain**
- `pushState()` & `replaceState()` ändern nur die **URL-Leiste**, nicht den Inhalt automatisch

---

## ✅ Zusammenfassung

| Was du tun willst                  | Methode                 |
|------------------------------------|--------------------------|
| Seite zurück                      | `history.back()`         |
| Seite vor                         | `history.forward()`      |
| Dynamisch URL ändern              | `history.pushState()`    |
| Verlauf manipulieren ohne Reload | `history.replaceState()` |
| Seitennavigation auslesen         | `history.length`         |
