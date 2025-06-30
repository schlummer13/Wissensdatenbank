# `<p>` – Absatz (Paragraph)

## 🧩 Funktion

Das `<p>`-Element steht für „Paragraph“ und wird verwendet, um **Fließtext in Absätze zu gliedern**.  
Es sorgt für **lesbare, semantisch getrennte Textblöcke**, wie man sie aus klassischen Dokumenten oder Büchern kennt.

> 📌 Jeder `<p>`-Block stellt einen **eigenständigen Textabschnitt** dar – mit Abstand nach oben und unten (per CSS vordefiniert).

---

## ✅ Verwendung

```html
<p>Dies ist ein einfacher Fließtextabsatz.</p>
```

Der Text wird **automatisch umbrochen** und erhält durch den Browser einen **sichtbaren Abstand zum nächsten Element** – üblicherweise durch `margin`.

---

## 🔧 Mögliche Attribute

| Attribut | Beschreibung |
|----------|--------------|
| `id`     | Ermöglicht das gezielte Ansteuern per Ankerlink (z. B. `#absatz1`) |
| `class`  | Zuweisung von CSS-Klassen für Design & Stil |
| `style`  | Direktes Inline-Styling (z. B. `text-align`, `color`) |
| `title`  | Tooltip-Text beim Mouseover |
| `lang`   | Sprachkennzeichnung für Screenreader (z. B. `lang="en"`) |
| `dir`    | Schreibrichtung (z. B. `ltr`, `rtl`) für internationale Inhalte |

---

## 🎨 Beispiel mit CSS-Styling

```html
<p class="info-text">Dieser Absatz ist wichtig.</p>
```

```css
.info-text {
  font-style: italic;
  background-color: #f5f5f5;
  padding: 1em;
  border-left: 4px solid #0077cc;
}
```

---

## 📏 Mehrere Absätze im Fließtext

```html
<p>Einführung in das Thema Webentwicklung. HTML ist die Grundlage...</p>

<p>Im nächsten Abschnitt betrachten wir CSS – das für das Styling zuständig ist.</p>
```

👉 Jeder `<p>`-Tag erzeugt einen **eigenständigen Textblock** mit Abstand zum vorherigen.

---

## ⚠️ Einschränkungen

- `<p>` darf **keine Blockelemente** enthalten, z. B. keine `<div>`, `<section>`, `<ul>` im Inneren.
- Verschachtelung von `<p>`-Tags ist **nicht erlaubt**:
  ```html
  <p>Dies ist <p>nicht gültig</p></p> ❌
  ```

---

## ♿ Barrierefreiheit & Semantik

- `<p>`-Elemente sind für **Screenreader klar verständlich** als Absätze.
- Kombiniert mit `lang` und `dir` kann die **sprachliche und richtungsbezogene Darstellung verbessert** werden.
- Für spezielle Bedeutung (z. B. Zitate, Definitionen, Warnhinweise) können ergänzend semantische Elemente wie `<blockquote>`, `<mark>`, `<strong>` verwendet werden.

---

## ❌ Häufige Fehler

| Fehler                                       | Korrekte Alternative                      |
|---------------------------------------------|-------------------------------------------|
| Absatz durch `<br><br>` statt `<p>`         | Verwende `<p>` für semantische Absätze    |
| Verschachtelte `<p>`-Elemente               | `<p>` darf **nicht** in sich selbst vorkommen |
| `<p>` um ganze Layoutbereiche (`<div>`)     | Layout gehört **außerhalb** von `<p>`     |
| Nutzung nur zur Formatierung ohne Bedeutung | Nutze `<p>` **nur für echten Fließtext**  |

---

## 📚 Fazit

Das `<p>`-Element gehört zu den **fundamentalsten HTML-Tags** und ist unerlässlich für gut strukturierte Texte. Es sorgt nicht nur für visuelle Gliederung, sondern gibt dem Inhalt auch **semantische Bedeutung** – wichtig für Lesbarkeit, SEO und Barrierefreiheit.
