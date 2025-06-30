# `<dfn>` – Begriff definieren (Definition Element)

## 🧩 Funktion

Das `<dfn>`-Element wird verwendet, um **einen Begriff zu kennzeichnen, der an dieser Stelle definiert oder erklärt wird**.  
Es hebt **semantisch** hervor, dass es sich um den **ersten Auftritt eines Begriffs** handelt, der für das Verständnis des Inhalts wichtig ist.

> 📌 `<dfn>` hilft Lesern, Screenreadern und Suchmaschinen, **Definitionen zu erkennen und besser zu interpretieren**.

---

## ✅ Verwendung

```html
<p>
  Ein <dfn id="algorithmus">Algorithmus</dfn> ist eine Schritt-für-Schritt-Anleitung zur Lösung eines Problems.
</p>
```

👉 Der Begriff „Algorithmus“ wird hier **definiert** – durch das `<dfn>` erhält er semantische Bedeutung.

---

## 🔧 Attribute

| Attribut | Beschreibung |
|----------|--------------|
| `id`     | Wichtig, um z. B. mit `aria-describedby` oder internen Links darauf zu verweisen |
| `title`  | Zusätzliche Beschreibung als Tooltip (optional) |
| `lang`   | Sprache des Begriffs (z. B. `lang="en"` bei fremdsprachigen Termini) |
| `class`  | Für visuelles Styling |
| `style`  | Direktes CSS-Styling (Inline) |

---

## 🎨 Beispiel mit Tooltip und Styling

```html
<dfn id="ml" title="Machine Learning">ML</dfn>
```

```css
dfn {
  font-style: italic;
  border-bottom: 1px dotted #999;
  cursor: help;
}
```

👉 So wird der definierte Begriff **optisch kenntlich gemacht**, z. B. in Glossaren oder Fachtexten.

---

## 🧠 Best Practices

| Empfehlung                            | Warum? |
|--------------------------------------|--------|
| Nur beim ersten Auftreten im Text    | `<dfn>` ist für die **Einführung eines Begriffs** gedacht |
| Mit `id` kombinieren                 | Ermöglicht Link-Ziele für Glossare oder Referenzen |
| In Kombination mit `aria-describedby` oder `<abbr>` nutzbar | Für barrierefreie Begriffsdefinitionen |

---

## 📚 Beispiel: Definition mit Bezug

```html
<p>
  Das Konzept des <dfn id="scraping">Scrapings</dfn> beschreibt das automatisierte Auslesen von Webseiteninhalten.
</p>

<p>
  Weitere Informationen zu <a href="#scraping">Scraping</a> findest du im Glossar.
</p>
```

---

## ♿ Barrierefreiheit & SEO

- Screenreader erkennen `<dfn>` als „Definierter Begriff“ (sofern korrekt verwendet)
- In Verbindung mit `title` oder einem `<abbr>` kann die Bedeutung zusätzlich **vorgelesen oder angezeigt** werden
- Strukturierte Begriffsdefinitionen sind **gut für Suchmaschinen**, insbesondere bei technischem oder wissenschaftlichem Inhalt

---

## ❌ Häufige Fehler

| Fehler                                     | Besser                                      |
|--------------------------------------------|---------------------------------------------|
| `<dfn>` für jedes Vorkommen des Begriffs   | Nur für die **erste Erklärung oder Definition** verwenden |
| Keine Verbindung zu erklärendem Text       | Immer mit Erklärung oder Beschreibung verbinden |
| Verwendung als Stilmittel (nur visuell)    | Dafür lieber `<span>` + `class` nutzen      |

---

## ✅ `<dfn>` vs. `<abbr>` vs. `<var>`

| Element   | Zweck                         | Typischer Einsatz                             |
|-----------|-------------------------------|------------------------------------------------|
| `<dfn>`   | Definition eines Begriffs     | Erster Auftritt eines Fachbegriffs             |
| `<abbr>`  | Abkürzung mit Langform        | z. B. „<abbr title='HyperText Markup Language'>HTML</abbr>“ |
| `<var>`   | Variable/Symbol               | z. B. in Formeln, Code, Mathematik             |

---

## 📚 Fazit

`<dfn>` ist ein **semantisch starkes HTML-Element**, das hilft, **Begriffe im Kontext korrekt zu definieren**.  
Es verbessert sowohl die **Zugänglichkeit als auch die Struktur** technischer, wissenschaftlicher und erklärender Inhalte.
