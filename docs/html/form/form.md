# `<form>` – Formularcontainer

## 🧩 Funktion

Das `<form>`-Element definiert einen **Formularbereich** in einer Webseite, in dem **Benutzereingaben erfasst und an einen Server gesendet** werden. Es enthält eine oder mehrere Eingabekomponenten wie `<input>`, `<textarea>`, `<select>`, `<button>` etc.

Ein Formular kann sowohl **sichtbare Eingaben** als auch **versteckte Werte** enthalten und bietet verschiedene **Methoden zur Übertragung** – z. B. über `GET` oder `POST`.

---

## ✅ Basisverwendung

```html
<form action="/absenden" method="post">
  <label for="email">E-Mail:</label>
  <input name="email" type="email" required />
  <button type="submit">Senden</button>
</form>
```

**Was passiert?**  
👉 Die E-Mail-Adresse wird per HTTP-POST an die URL `/absenden` geschickt, wenn der Nutzer auf „Senden“ klickt.

---

## 🔧 Wichtige Attribute von `<form>`

| Attribut        | Beschreibung |
|-----------------|--------------|
| `action`        | Ziel-URL, an die das Formular beim Absenden gesendet wird |
| `method`        | Übertragungsmethode: `get` (URL-Parameter) oder `post` (unsichtbar im Body) |
| `autocomplete`  | Aktiviert oder deaktiviert die automatische Vervollständigung (`on`/`off`) |
| `enctype`       | Kodierung der gesendeten Daten – wichtig bei Datei-Uploads (z. B. `multipart/form-data`) |
| `target`        | Ziel, in dem das Ergebnis geöffnet wird (`_self`, `_blank`, `_parent`, `_top`) |
| `novalidate`    | Unterdrückt die HTML5-Eingabevalidierung |
| `name`          | Name des Formulars (zur Identifikation in Skripten) |
| `accept-charset`| Zeichencodierung beim Absenden (z. B. `UTF-8`) |

---

## 📦 `method="get"` vs. `method="post"`

| Methode | Beschreibung | Typisches Einsatzgebiet |
|--------|---------------|--------------------------|
| `get`  | Daten werden als URL-Parameter angehängt (sichtbar!) | Suchfelder, Filter |
| `post` | Daten werden im Request-Body übermittelt | Login-Formulare, sensible Daten, Datei-Uploads |

Beispiel `get`:

```html
<form action="/suche" method="get">
  <input type="text" name="q" placeholder="Suchbegriff" />
  <button type="submit">Suchen</button>
</form>
```

👉 ergibt z. B.: `/suche?q=html`

---

## 🧪 Beispiel mit Datei-Upload (`enctype`)

```html
<form action="/upload" method="post" enctype="multipart/form-data">
  <label for="datei">Datei hochladen:</label>
  <input type="file" id="datei" name="datei" />
  <button type="submit">Upload</button>
</form>
```

**Wichtig:**  
📌 Ohne `enctype="multipart/form-data"` funktioniert der Datei-Upload nicht korrekt.

---

## 🎯 Beispiel mit `target="_blank"`

```html
<form action="https://example.com/suchen" method="get" target="_blank">
  <input type="text" name="q" placeholder="Suche auf externer Seite" />
  <button type="submit">Suchen</button>
</form>
```

**Was passiert?**  
👉 Die Ergebnisseite wird in einem **neuen Tab** geöffnet.

---

## 🧠 HTML5: Validierung abschalten

```html
<form action="/feedback" method="post" novalidate>
  <input type="email" name="email" placeholder="Email (optional)" />
  <button type="submit">Ohne Prüfung absenden</button>
</form>
```

---

## 🧾 Best Practices

- Immer passende **Labels mit Inputs verknüpfen** (`<label for="...">`)
- Eingabefelder sinnvoll gruppieren mit `<fieldset>` und `<legend>`
- `required`, `minlength`, `type` usw. zur Vorab-Validierung verwenden
- Verwende JavaScript nur als Ergänzung, **nicht als Ersatz** für Formularlogik
- Verwende `name`-Attribute in allen Eingabefeldern – sie bestimmen die **Schlüssel** der gesendeten Daten

---

## 📚 Fazit

Das `<form>`-Tag ist das Herzstück jeder interaktiven Webseite. Es bildet den Rahmen, in dem Benutzereingaben gesammelt, verarbeitet und übermittelt werden. Mit den richtigen Attributen und einer sauberen Struktur kann ein Formular **intuitiv, sicher und zugänglich** gestaltet werden.
