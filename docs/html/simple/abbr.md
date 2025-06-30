# `<abbr>` – Abkürzungen semantisch markieren

## 🧩 Funktion

Das `<abbr>`-Element (Abbreviation) dient dazu, **Abkürzungen oder Akronyme** im Fließtext **semantisch zu kennzeichnen**.  
Dadurch wird der **volle Begriff** über das `title`-Attribut hinterlegt, sodass Browser und Screenreader diesen anzeigen oder aussprechen können.  
Besonders nützlich für **Barrierefreiheit, SEO, Fachbegriffe und internationale Inhalte**.

> 📌 Das `<abbr>`-Tag hilft Leser:innen sowie Maschinen, den vollständigen Ausdruck einer Abkürzung zu verstehen.

---

## ✅ Verwendung

```html
<p>Die Konferenz wird von der <abbr title="World Health Organization">WHO</abbr> organisiert.</p>
```

👉 Beim Mouseover wird ein Tooltip mit „World Health Organization“ angezeigt.  
Screenreader können je nach Einstellung „World Health Organization“ statt „W-H-O“ vorlesen.

---

## 🔧 Attribute

| Attribut | Beschreibung |
|----------|--------------|
| `title`  | Erforderlich – enthält die vollständige Langform |
| `lang`   | Angabe der Sprache des abgekürzten Begriffs |
| `class`  | Für visuelles Styling via CSS |
| `id`     | Für JS oder Ankerverlinkung |
| `style`  | Inline-Styling (nur bei Bedarf empfohlen) |

---

## 🎨 Beispiel mit CSS

```html
<abbr class="definition" title="As Soon As Possible">ASAP</abbr>
```

```css
.definition {
  border-bottom: 1px dotted #888;
  cursor: help;
}
```

👉 So wirkt die Abkürzung wie ein interaktives Glossar-Element.

---

## 🧠 Best Practices

| Empfehlung                        | Warum? |
|----------------------------------|--------|
| Immer mit `title`-Attribut       | Tooltip + maschinenlesbar |
| Nur echte Abkürzungen verwenden  | Keine ganzen Sätze oder Floskeln |
| Mit `lang` kennzeichnen, wenn nötig | Besonders bei Fremdsprachen |

### Beispiel mit Sprachangabe:

```html
<abbr title="HyperText Markup Language" lang="en">HTML</abbr>
```

👉 Besonders hilfreich für Screenreader, um z. B. englische Akronyme korrekt auszusprechen.

---

## ♿ Barrierefreiheit

- Ermöglicht **verständliche Inhalte für Screenreader-Nutzer:innen**
- Tooltip beim Hover hilft allen Nutzer:innen, die Bedeutung zu verstehen
- Sehr sinnvoll bei Fachtexten, technischen Begriffen oder internationalen Abkürzungen

---

## ❌ Häufige Fehler

| Fehler                                         | Besser                                          |
|------------------------------------------------|--------------------------------------------------|
| `<abbr>` ohne `title`                         | `title` ist Pflicht für Bedeutung               |
| Ganze Sätze in `title`                        | Nur **Begriff** oder **Langform** hinterlegen   |
| Styling statt Bedeutung                       | Nutze `<abbr>` nur für **echte Abkürzungen**    |
| Verzicht bei technischen Begriffen            | `<abbr>` aktiv nutzen für Barrierefreiheit      |

---

## 📚 Fazit

Das `<abbr>`-Element bringt **Semantik, Zugänglichkeit und Verständlichkeit** in deine HTML-Seite.  
Es ist ein **kleines, aber mächtiges Werkzeug**, um Inhalte **klarer, barrierefreier und professioneller** darzustellen – insbesondere in Fachtexten, Dokumentationen und mehrsprachigen Webseiten.
