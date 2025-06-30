# `<select>` – Dropdown-Auswahlliste

## 🧩 Funktion

Das `<select>`-Element wird verwendet, um dem Benutzer eine **Auswahlliste** mit **vordefinierten Optionen** anzubieten. Es wird häufig für Formulare verwendet, bei denen der Nutzer **eine oder mehrere Optionen** aus einer Liste wählen soll.

Die auswählbaren Werte werden in `<option>`-Elementen definiert, die innerhalb des `<select>`-Elements liegen.

---

## ✅ Grundstruktur

```html
<select name="land">
  <option value="de">Deutschland</option>
  <option value="at">Österreich</option>
  <option value="ch">Schweiz</option>
</select>
```

**Was passiert?**  
👉 Der Benutzer sieht eine Dropdown-Liste und kann **eine der drei Länderoptionen** auswählen. Der Wert (`value`) wird beim Absenden des Formulars übermittelt.

---

## 🔧 Wichtige Attribute

| Attribut        | Beschreibung |
|-----------------|--------------|
| `name`          | Bezeichner für die Serververarbeitung beim Absenden |
| `id`            | Eindeutige ID für Verbindung mit `<label>` |
| `multiple`      | Erlaubt Mehrfachauswahl (Strg / Cmd oder Shift) |
| `size`          | Legt Anzahl der sichtbaren Optionen fest (wirksam nur ohne Dropdown) |
| `required`      | Markiert das Feld als Pflichtfeld |
| `disabled`      | Deaktiviert die gesamte Auswahlliste |
| `autofocus`     | Der Fokus liegt beim Laden der Seite direkt auf dem Element |

---

## 🔘 `<option>`-Attribute

| Attribut        | Beschreibung |
|-----------------|--------------|
| `value`         | Wert, der beim Absenden übermittelt wird |
| `selected`      | Legt fest, welche Option vorausgewählt ist |
| `disabled`      | Diese Option ist nicht auswählbar |
| (ohne value)    | Wenn `value` fehlt, wird der Inhalt als Wert verwendet |

---

## 🧪 Beispiele

### 1. ✅ Mit vorausgewähltem Wert

```html
<label for="farbe">Lieblingsfarbe:</label>
<select id="farbe" name="farbe">
  <option value="rot">Rot</option>
  <option value="blau" selected>Blau</option>
  <option value="gruen">Grün</option>
</select>
```

👉 „Blau“ ist standardmäßig vorausgewählt.

---

### 2. 🔄 Mit Platzhalter-Option

```html
<select name="stadt" required>
  <option value="" disabled selected>Bitte Stadt wählen</option>
  <option value="berlin">Berlin</option>
  <option value="muenchen">München</option>
  <option value="koeln">Köln</option>
</select>
```

👉 Der erste Eintrag dient als **Platzhalter** – es muss aktiv eine gültige Stadt gewählt werden.

---

### 3. 🎯 Mehrfachauswahl mit `multiple`

```html
<select name="interessen[]" multiple size="4">
  <option value="sport">Sport</option>
  <option value="musik">Musik</option>
  <option value="reisen">Reisen</option>
  <option value="lesen">Lesen</option>
</select>
```

👉 Nutzer kann mit **Strg (Windows)** oder **Cmd (Mac)** mehrere Optionen auswählen. Das `[]` im `name`-Attribut überträgt mehrere Werte als Array.

---

### 4. 🚫 Optionen deaktivieren

```html
<select name="bundesland">
  <option value="" disabled selected>Bitte wählen</option>
  <option value="bw">Baden-Württemberg</option>
  <option value="by" disabled>Bayern (nicht verfügbar)</option>
  <option value="he">Hessen</option>
</select>
```

👉 „Bayern“ erscheint, ist aber **nicht auswählbar**.

---

### 5. 📁 Optionen gruppieren mit `<optgroup>`

```html
<select name="forschung">
  <optgroup label="Naturwissenschaften">
    <option value="physik">Physik</option>
    <option value="biologie">Biologie</option>
  </optgroup>
  <optgroup label="Geisteswissenschaften">
    <option value="geschichte">Geschichte</option>
    <option value="philosophie">Philosophie</option>
  </optgroup>
</select>
```

👉 Gruppiert verwandte Optionen logisch – gut für lange Listen und Barrierefreiheit.

---

## ♿ Barrierefreiheit

- Verwende immer ein zugehöriges `<label for="...">`, um Screenreadern die Zuordnung zu erleichtern.
- Gruppiere viele Optionen mit `<optgroup>`, um Übersichtlichkeit zu schaffen.
- Vermeide Platzhalter-Optionen ohne `disabled`, da sie sonst fälschlich als gültige Auswahl gesendet werden könnten.

---

## 🧾 Best Practices

- Für komplexere Auswahl-Interfaces nutze zusätzliche **JavaScript-Plugins** wie [Select2](https://select2.org/) oder native `<datalist>`.
- Bei Mehrfachauswahl die Optionen im Backend als Array behandeln (`interessen[]`).
- Teste `multiple`-Selects auch mit Tastatursteuerung.
- Nutze `required` und `disabled`, um Eingaben besser zu kontrollieren.

---

## 📚 Fazit

Das `<select>`-Element ist ideal, um Benutzern **strukturierte und eingeschränkte Auswahlmöglichkeiten** zu bieten. In Kombination mit `<option>` und `<optgroup>` kannst du benutzerfreundliche, barrierefreie und semantisch saubere Auswahlfelder erstellen.
