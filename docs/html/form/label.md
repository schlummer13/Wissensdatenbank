# `<label>` – Beschriftung für Formularfeld

## 🧩 Funktion

Ein `<label>` ist ein **semantisches HTML-Element**, das einem Eingabefeld eine **klar erkennbare Bezeichnung** zuweist.  
Es ist nicht nur **optisch hilfreich**, sondern auch **essentiell für Barrierefreiheit**: Screenreader können dadurch Eingabefelder korrekt interpretieren.

Ein korrektes `<label>` erhöht die Benutzerfreundlichkeit und hilft, Eingabefehler zu vermeiden.

---

## ✅ Standardverwendung

```html
<label for="email">E-Mail</label>
<input id="email" type="email" />
```

**Was passiert?**  
👉 Wenn der Benutzer auf „E-Mail“ klickt, erhält das zugehörige Eingabefeld den Fokus – sehr nützlich für die Bedienung per Maus oder Screenreader.

---

## 🔧 Wichtige Attribute

| Attribut        | Beschreibung |
|-----------------|--------------|
| `for`           | Verknüpft das Label mit dem Element, dessen `id` übereinstimmt |
| `class`, `style`| Für CSS-Klassen oder Inline-Design |
| `form`          | Optional: Referenz auf ein Formular außerhalb des Labels (selten genutzt) |

---

## 🧪 Varianten

### 1. ✅ Umschließendes Label (ohne `for`)

```html
<label>
  Passwort:
  <input type="password" name="passwort" />
</label>
```

👉 **Der Input ist im Label eingeschlossen**. Praktisch für einfache Formulare, aber **nicht ideal für Barrierefreiheit**, da der `for`-Bezug fehlt.

### 2. ♿ Mit `for` und `id`

```html
<label for="plz">Postleitzahl:</label>
<input id="plz" name="plz" type="text" />
```

👉 **Empfohlene Methode** für Screenreader, Formulare und Browseroptimierung.

### 3. 💡 Kombination mit `fieldset`

```html
<fieldset>
  <legend>Geschlecht</legend>
  <label><input type="radio" name="gender" value="m" /> Männlich</label>
  <label><input type="radio" name="gender" value="w" /> Weiblich</label>
</fieldset>
```

👉 **Keine `for`-Attribute notwendig**, da Inputs **innerhalb des Labels** eingebettet sind.

---

## 🎨 Styling-Tipps

```css
label {
  display: block;
  font-weight: bold;
  margin-bottom: 0.5em;
}
```

👉 Gute Labels sind **deutlich erkennbar**, stehen **oberhalb** der Inputs und sind gut lesbar.

---

## ♿ Barrierefreiheit

- Labels sind **essentiell** für barrierefreie Formulare.
- **Screenreader** lesen das Label zusammen mit dem Eingabefeld.
- Für **Checkboxen/Radio-Buttons** unbedingt mit Label arbeiten – sonst sind sie schwer bedienbar.
- Bei `aria-labelledby` in Custom Controls können Labels auch als **referenzierter Text** dienen.

---

## 🔥 Best Practices

- Immer **eindeutige `id`-Werte** verwenden – kein Duplikat!
- Labels so platzieren, dass sie vor dem zugehörigen Feld stehen – für bessere Lesbarkeit.
- Kein `<br>` im Label – verwende besser `display: block` in CSS.
- Keine Labels durch reine Platzhalter ersetzen (`placeholder ≠ label`) – Platzhalter verschwinden beim Tippen und sind nicht barrierefrei.

---

## 📚 Fazit

Ein gut eingesetztes `<label>` ist **mehr als nur Text** – es ist eine essenzielle Hilfe für Benutzerfreundlichkeit, Barrierefreiheit und klare Formularstruktur.  
Wer `<label>` korrekt verwendet, baut **zugängliche und professionelle Webformulare**.
