# `<span>` – Inline-Container für Textauszeichnung

## 🧩 Funktion

Das `<span>`-Element ist ein **semantikfreies, generisches Inline-Element**, das verwendet wird, um **einzelne Textabschnitte oder Inline-Inhalte gezielt zu markieren oder zu stylen**.  
Im Gegensatz zu `<div>` (Block-Element) wirkt `<span>` **nicht layoutverändernd**, sondern bleibt innerhalb des Textflusses.

> 📌 Verwende `<span>` immer dann, wenn du **Text innerhalb eines Satzes** formatieren oder logisch markieren willst – ohne dass daraus ein eigener Block wird.

---

## ✅ Verwendung

```html
<p>Das Wort <span class="highlight">wichtig</span> ist hervorgehoben.</p>
```

👉 Der markierte Abschnitt kann per CSS formatiert oder über JavaScript angesprochen werden.

---

## 🔧 Mögliche Attribute

| Attribut  | Beschreibung |
|-----------|--------------|
| `class`   | Ermöglicht CSS-Styling über definierte Klassen |
| `style`   | Inline-CSS zur direkten Formatierung (z. B. `color`, `font-weight`) |
| `id`      | Individuelle Identifikation (z. B. für JavaScript oder Anker) |
| `title`   | Tooltip-Text beim Mouseover |
| `lang`    | Sprachkennung für Screenreader |
| `data-*`  | Eigene HTML5-Datenattribute für JS (z. B. `data-status="active"`) |

---

## 🎨 Beispiel mit CSS-Klasse

```html
<style>
  .highlight {
    background-color: yellow;
    font-weight: bold;
  }
</style>

<p>Dies ist ein <span class="highlight">wichtiger</span> Hinweis.</p>
```

---

## 🧠 Wann `<span>` verwenden?

| Situation                                     | Element |
|-----------------------------------------------|---------|
| Du möchtest Text innerhalb eines Absatzes visuell hervorheben | ✅ `<span>` |
| Du willst ein ganzes Layout-Element strukturieren | ❌ besser `<div>` |
| Du brauchst semantische Bedeutung wie "Wichtig" | ❌ besser `<strong>` oder `<em>` |

---

## 📐 Unterschiede zu ähnlichen Elementen

| Element   | Block/Inline | Semantik       | Typischer Einsatz                        |
|-----------|--------------|----------------|------------------------------------------|
| `<span>`  | Inline       | Keine          | Styling / JS-Zugriff auf Textabschnitte  |
| `<div>`   | Block        | Keine          | Layoutstruktur                           |
| `<strong>`| Inline       | Wichtigkeit    | Semantisch hervorgehobener Text          |
| `<em>`    | Inline       | Betonung       | Hervorhebung durch Betonung (z. B. *wirklich*) |

---

## ❌ Häufige Fehler

| Fehler                                       | Besser                                       |
|----------------------------------------------|----------------------------------------------|
| `<span>` als Container für ganze Layoutblöcke | Verwende `<div>` für strukturierende Elemente |
| `<span>` für semantisch bedeutenden Text      | Nutze `<strong>` oder `<em>` für echte Bedeutung |
| Inline-JavaScript in `<span onclick="...">`   | Nutze `addEventListener` über JS             |

---

## ♿ Barrierefreiheit

- `<span>` hat **keine Bedeutung** für Screenreader – gut für rein visuelle Hervorhebungen
- Wenn Bedeutung vorhanden ist (z. B. „Fehler“), sollte zusätzlich eine **ARIA-Rolle oder semantisches Tag** verwendet werden
- Mit `lang` kann z. B. ein Fremdwort markiert werden:  
  ```html
  <span lang="fr">bonjour</span>
  ```

---

## 📚 Fazit

`<span>` ist ein vielseitiges Werkzeug zur **Inline-Auszeichnung ohne strukturelle Wirkung**. Es ist besonders nützlich für **Designzwecke, JS-Zugriff oder Detailanpassungen** innerhalb von Text – solange du dir bewusst bist, dass es **keine semantische Bedeutung trägt**.
