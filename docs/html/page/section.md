# `<section>` – Thematische Gliederung

## 🧩 Funktion

Das `<section>`-Element dient dazu, **inhaltlich zusammengehörige Inhalte** in einem Dokument logisch zu **strukturieren und zu gliedern**.  
Es stellt einen eigenständigen **Themenblock** innerhalb einer Seite dar – vergleichbar mit einem Kapitel oder Absatz in einem Buch.

> 📌 Jede `<section>` sollte in der Regel eine **Überschrift** enthalten (`<h1>`–`<h6>`) und in sich **semantisch sinnvoll** sein.

---

## ✅ Verwendung

```html
<section>
  <h2>Unsere Leistungen</h2>
  <p>Wir bieten Beratung, Webentwicklung und Data Science an.</p>
</section>
```

👉 Die Section bildet eine klar definierte thematische Einheit mit Titel und Inhalt.

---

## 🔧 Attribute

| Attribut   | Beschreibung                                              |
|------------|-----------------------------------------------------------|
| `id`       | Ermöglicht interne Sprungziele und Navigation             |
| `class`    | Gruppierung für CSS-Design                               |
| `style`    | Direktes Inline-Styling (z. B. Padding, Farben)           |
| `aria-labelledby` | Zur barrierefreien Verknüpfung mit Überschrift    |
| `data-*`   | Benutzerdefinierte Daten für JS oder dynamische Inhalte  |

---

## 🧠 Typische Einsatzzwecke

| Kontext                        | Beispiel                                      |
|-------------------------------|-----------------------------------------------|
| Inhaltliche Kapitel            | Ein Bereich zu „Unsere Leistungen“           |
| Mehrsprachige Inhalte          | Unterschiedliche Sprachen in separaten Sections |
| FAQ oder Help-Bereiche         | Jeder Abschnitt eine Frage + Antwort          |
| Thematisch gegliederte Landingpage | Features, Testimonials, Preise etc.     |

---

## 🎨 Beispiel mit Navigation

```html
<nav>
  <ul>
    <li><a href="#leistungen">Leistungen</a></li>
    <li><a href="#team">Team</a></li>
  </ul>
</nav>

<section id="leistungen">
  <h2>Unsere Leistungen</h2>
  <p>Webentwicklung, Automatisierung und SEO.</p>
</section>

<section id="team">
  <h2>Unser Team</h2>
  <p>Wir sind erfahrene Entwickler und Analysten.</p>
</section>
```

---

## ♿ Barrierefreiheit (a11y)

- Screenreader erkennen `<section>` als **eigenständigen Inhaltsbereich**
- Durch korrekte Verwendung von Überschriften und IDs kann eine **logische Navigation** hergestellt werden
- Kombination mit `aria-labelledby` möglich, z. B.:

```html
<section aria-labelledby="features-title">
  <h2 id="features-title">Features</h2>
  <p>Unsere Software kann...</p>
</section>
```

---

## ❌ Häufige Fehler

| Fehler                                           | Besser                                              |
|--------------------------------------------------|-----------------------------------------------------|
| `<section>` ohne Überschrift                    | Immer mit `<h2>`–`<h6>` einführen                  |
| Als Layout-Ersatz verwendet                     | Für rein visuelle Zwecke besser `<div>` nutzen     |
| Für zu kurze oder unklare Inhalte verwendet     | Inhalt sollte ein klar umrissenes Thema darstellen |

---

## 🔄 Unterschied zu ähnlichen Elementen

| Element     | Zweck                                         |
|-------------|-----------------------------------------------|
| `<section>` | Inhaltlich gegliederter Themenblock            |
| `<div>`     | Neutrales Container-Element ohne Semantik     |
| `<article>` | Eigenständiger, von der Seite loslösbarer Inhalt |
| `<aside>`   | Ergänzende Inhalte wie Sidebar oder Hinweisbox |
| `<main>`    | Einmaliger Hauptinhaltsbereich der Seite      |

---

## 📚 Fazit

`<section>` ist ein wichtiges semantisches HTML-Element zur **Strukturierung komplexer Inhalte**.  
Es hilft sowohl Lesern als auch Maschinen (z. B. Screenreadern oder Suchmaschinen), den **logischen Aufbau** der Seite zu verstehen.