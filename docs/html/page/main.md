# `<main>` – Hauptinhalt der Seite

## 🧩 Funktion

Das `<main>`-Element kennzeichnet den **zentralen inhaltlichen Bereich** einer Webseite – also den Teil, der sich **direkt auf das Thema oder den Zweck der Seite** bezieht.

Es enthält die Hauptinformationen, die den eigentlichen Inhalt der Seite darstellen, **ohne Navigation, Header, Footer oder Sidebar**.

> 📌 `<main>` ist ein **semantisches Blockelement**, das **nur einmal pro Seite** vorkommen darf.

---

## ✅ Verwendung

```html
<main>
  <article>
    <h2>Blogartikel: HTML verstehen</h2>
    <p>HTML ist die Sprache des Webs...</p>
  </article>
</main>
```

👉 Der zentrale Artikel liegt innerhalb von `<main>` – Navigation, Logo oder Footer sind außen vor.

---

## 🔧 Attribute

| Attribut     | Beschreibung                                             |
|--------------|----------------------------------------------------------|
| `id`         | Zur gezielten Referenz, z. B. in Skip Links              |
| `class`      | Für CSS-Design oder Layout-Zuweisung                     |
| `style`      | Inline-Styling (z. B. Hintergrund, Abstände)             |
| `role="main"`| Optional für Barrierefreiheit, wenn nötig (meist implizit) |
| `data-*`     | Eigene Daten für JavaScript-Logik                        |

---

## 🧠 Besonderheiten

- **Nur ein `<main>`-Element pro Dokument erlaubt**
- `<main>` darf **nicht** in `<header>`, `<footer>`, `<article>` oder `<aside>` enthalten sein
- Soll den **zentralen inhaltlichen Fokus** der Seite abbilden (z. B. Blogtext, Produktbeschreibung, Dashboard-Daten)

---

## 🎯 Typische Inhalte im `<main>`

| Inhaltstyp              | Beispiel                             |
|-------------------------|--------------------------------------|
| Blog-Artikel            | `<article>` mit Beiträgen            |
| Hauptinformationen      | Text, Bilder, Videos zur Seite       |
| Dynamischer Content     | Dashboard-Komponenten, Tabellen      |
| Eingabebereich (Form)   | Hauptformular auf einer Seite        |

---

## 🎨 Beispiel mit CSS

```css
main {
  padding: 2rem;
  max-width: 800px;
  margin: auto;
  background: #fff;
}
```

---

## ♿ Barrierefreiheit (a11y)

- Screenreader erkennen `<main>` automatisch als **zentralen Navigationspunkt**
- Nützlich in Kombination mit „Skip to main content“-Links:
  
```html
<a href="#main-content" class="skip-link">Zum Inhalt springen</a>
<main id="main-content">
  ...
</main>
```

---

## ❌ Häufige Fehler

| Fehler                                | Richtige Anwendung                                |
|---------------------------------------|----------------------------------------------------|
| Mehrere `<main>`-Elemente auf einer Seite | Nur **ein** Hauptbereich pro Seite                |
| `<main>` innerhalb von `<header>` o. ä. | Hauptinhalt sollte **außerhalb** semantischer Wrapper sein |
| Hauptinhalt ohne `<main>`             | `<main>` verbessert Struktur, SEO und Zugänglichkeit |

---

## 🔄 Vergleich zu ähnlichen Elementen

| Element   | Zweck                                     |
|-----------|--------------------------------------------|
| `<main>`  | **Einzelner zentraler Inhaltsbereich**     |
| `<section>` | Thematische Unterteilung **innerhalb** von `<main>` |
| `<article>` | Eigenständiger Inhalt wie Blogpost       |
| `<div>`    | Neutrale Gruppierung ohne Semantik        |

---

## 📚 Fazit

Das `<main>`-Element bietet eine **klare, zugängliche Struktur** für den wichtigsten Seiteninhalt.  
Es ist für moderne, semantisch saubere Webseiten **unerlässlich** – besonders im Zusammenspiel mit `<header>`, `<nav>` und `<footer>`.

