# `<q>` – Kurzes Inline-Zitat

## 🧩 Funktion

Das `<q>`-Element („quote“) wird verwendet, um **kurze Zitate direkt im Textfluss** zu kennzeichnen. Es ist ein **semantisches Inline-Element**, das standardmäßig **automatisch Anführungszeichen** um den enthaltenen Text setzt (je nach Spracheinstellung des Dokuments).

> 📌 `<q>` eignet sich für **einzelne Sätze, Phrasen oder wörtliche Aussagen** innerhalb eines Absatzes – nicht für längere Zitate (dafür `<blockquote>` verwenden).

---

## ✅ Verwendung

```html
<p>Steve Jobs sagte einst: <q>Stay hungry, stay foolish.</q></p>
```

👉 Das Zitat wird **automatisch in Anführungszeichen** gesetzt, z. B.:

> Steve Jobs sagte einst: “Stay hungry, stay foolish.”

(Je nach Spracheinstellung auch „deutsche Anführungszeichen“)

---

## 🔧 Attribute

| Attribut | Beschreibung |
|----------|--------------|
| `cite`   | URL zur Quelle des Zitats (optional, maschinenlesbar) |
| `lang`   | Sprache des Zitats (z. B. `lang="en"` für fremdsprachige Abschnitte) |
| `class`  | Für CSS-Styling |
| `style`  | Direktes Inline-Styling |
| `id`     | Individuelle Kennung, z. B. für JavaScript-Zugriff |

---

### Beispiel mit Quelle

```html
<p>
  Laut Einstein: <q cite="https://www.einstein-portal.de">Phantasie ist wichtiger als Wissen.</q>
</p>
```

> Der `cite`-Wert ist **nicht sichtbar**, aber dient Maschinen und Tools zur **Quellenverfolgung**.

---

## 🎨 Styling mit CSS (optional)

```css
q {
  quotes: "„" "“" "‚" "‘"; /* Deutsche Anführungszeichen */
  font-style: italic;
  color: #444;
}
```

👉 Damit kannst du **Anführungszeichen-Stile kontrollieren** oder entfernen:

```css
q {
  quotes: none;
}
```

---

## 🧠 Unterschied zu `<blockquote>`

| Merkmal          | `<q>` (Inline-Zitat)        | `<blockquote>` (Block-Zitat)               |
|------------------|-----------------------------|--------------------------------------------|
| Textlänge        | Kurz (ein Satz oder Ausdruck) | Länger (Absätze oder mehrere Sätze)       |
| Position         | Innerhalb eines Textflusses | Eingerückt / eigener Block                 |
| Anführungszeichen| Automatisch gesetzt         | Manuell mit `&bdquo;`, `&ldquo;` o. ä.     |
| Typische Anwendung| Zitat im Satz              | Zitat mit Quelle oder längerer Passage     |

---

## ♿ Barrierefreiheit & Semantik

- Screenreader erkennen `<q>` als Zitat
- Browser interpretieren es **sprachabhängig** → richtige Anführungszeichen bei korrekt gesetztem `lang`-Attribut
- Ideal zur semantischen Kennzeichnung von **wörtlichen Reden, Zitaten, Aussagen** im Text

---

## ❌ Häufige Fehler

| Fehler                                   | Besser                                       |
|------------------------------------------|----------------------------------------------|
| Zitate mit Anführungszeichen im `<p>` nur visuell | `<q>` nutzen für semantisch korrektes Zitat |
| Verwendung für lange Absätze             | Nutze `<blockquote>` statt `<q>`            |
| Keine Spracheinstellung (`lang`) bei fremdsprachigem Zitat | `lang="en"` oder `lang="fr"` ergänzen       |

---

## 📚 Fazit

Das `<q>`-Element ist das **richtige Mittel für kurze, eingebettete Zitate**. Es bringt semantische Bedeutung, sorgt für automatisch gesetzte Anführungszeichen und hilft beim barrierefreien und suchmaschinenfreundlichen Markieren von Aussagen.
