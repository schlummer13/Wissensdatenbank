# `<datalist>` – Eingabe mit Vorschlagsliste

## 🧩 Funktion

Das `<datalist>`-Element ermöglicht dem Benutzer die **freie Eingabe eines Wertes**, aber mit **vordefinierten Vorschlägen**, die beim Tippen angezeigt werden.  
Es funktioniert in Kombination mit einem `<input>`-Feld und verhält sich wie eine **Auto-Vervollständigung**, bei der die Werte **nicht** zwingend ausgewählt werden müssen.

---

## ✅ Grundstruktur

```html
<label for="stadt">Stadt:</label>
<input list="staedte" id="stadt" name="stadt" />
<datalist id="staedte">
  <option value="Berlin">
  <option value="Hamburg">
  <option value="München">
</datalist>
```

**Was passiert?**  
👉 Sobald der Benutzer zu tippen beginnt, schlägt der Browser passende Werte aus der Liste vor.

---

## 🔧 Wichtige Elemente & Attribute

### `<input>`-Element:

| Attribut | Beschreibung |
|----------|--------------|
| `list`   | Verweist auf die `id` des zugehörigen `<datalist>` |
| `name`   | Name für die Formularübertragung |
| `type`   | Funktioniert mit z. B. `text`, `email`, `search`, `url` |

### `<datalist>`-Element:

| Attribut | Beschreibung |
|----------|--------------|
| `id`     | Eindeutige ID, die vom Input referenziert wird |

### `<option>`-Element innerhalb von `<datalist>`:

| Attribut | Beschreibung |
|----------|--------------|
| `value`  | Vorgeschlagener Wert – wird angezeigt und kann übernommen werden |
| `label`  | Optional: alternativer Anzeigename (nicht von allen Browsern unterstützt) |

---

## 🧪 Beispiele

### 1. 🔤 Textfeld mit Vorschlägen

```html
<label for="browser">Lieblingsbrowser:</label>
<input list="browserliste" id="browser" name="browser" />

<datalist id="browserliste">
  <option value="Chrome">
  <option value="Firefox">
  <option value="Safari">
  <option value="Edge">
  <option value="Opera">
</datalist>
```

👉 Der Benutzer kann eigene Werte eingeben **oder** einen aus der Liste wählen.

---

### 2. 🌐 URL-Vorschläge

```html
<label for="website">Webseite:</label>
<input type="url" list="vorschlaege" name="website" />

<datalist id="vorschlaege">
  <option value="https://example.com">
  <option value="https://solago.de">
  <option value="https://openai.com">
</datalist>
```

👉 Vorschläge für häufig besuchte oder empfohlene URLs.

---

### 3. ✨ Mit vordefiniertem Wert + Vorschlägen

```html
<input list="sprachen" name="sprache" value="Deutsch" />

<datalist id="sprachen">
  <option value="Deutsch">
  <option value="Englisch">
  <option value="Französisch">
</datalist>
```

👉 „Deutsch“ ist vorausgefüllt, aber der Benutzer kann etwas anderes wählen oder eingeben.

---

## ⚠️ Einschränkungen

- `<datalist>` unterstützt **keine Gruppierung** wie `<optgroup>`.
- **Kein Mehrfachauswahl** – anders als bei `<select multiple>`.
- Styling ist browserabhängig und **nicht vollständig kontrollierbar via CSS**.
- **Nicht alle mobilen Browser** zeigen Vorschläge an (z. B. ältere iOS-Versionen).

---

## ♿ Barrierefreiheit

- Verwende ein `<label>` mit `for`, um die Verbindung zum Input herzustellen.
- Stelle sicher, dass der Kontext der Vorschläge klar ist – besonders bei ähnlichen Begriffen.
- `aria-autocomplete="list"` kann bei benutzerdefinierten Controls sinnvoll sein (nicht notwendig für natives `<datalist>`).

---

## 💡 Best Practices

- Verwende `<datalist>` für **kleine, bekannte Wertemengen** – z. B. Autovervollständigung, häufige Städte, Codes etc.
- Für größere Datenmengen oder dynamische Inhalte nutze **JavaScript-basierte Autocomplete-Komponenten**.
- Gib nur Vorschläge an, die für das Eingabefeld logisch und relevant sind.
- Stelle sicher, dass manuelle Eingaben **nicht fehlschlagen**, wenn sie nicht in der Liste stehen.

---

## 📚 Fazit

Das `<datalist>`-Element ist ein einfaches, aber sehr nützliches Werkzeug zur **Verbesserung der Usability**, ohne komplexes JavaScript. Es ist besonders gut geeignet, wenn Benutzer **freitextlich eingeben dürfen**, aber du sinnvolle Vorschläge anbieten möchtest.
