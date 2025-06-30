# 🧱 Semantisches HTML – Übersicht

## 🧩 Was bedeutet „semantisch“ in HTML?

**Semantisches HTML** bedeutet, dass HTML-Elemente **nicht nur zur Strukturierung**, sondern auch zur **Bedeutung von Inhalten** verwendet werden.  
Anstatt beliebige `<div>`- oder `<span>`-Container zu nutzen, setzt man auf spezialisierte Elemente wie `<header>`, `<article>`, `<nav>`, die dem Browser und Entwicklern **vermitteln, was ein Inhalt ist**, nicht nur wie er aussieht.

> 🧠 Semantik = Bedeutung

---

## ✅ Vorteile von semantischem HTML

| Vorteil                      | Beschreibung |
|------------------------------|--------------|
| 🔍 Bessere SEO               | Suchmaschinen verstehen Inhalte leichter (z. B. was ist Navigation, Hauptinhalt etc.) |
| ♿ Barrierefreiheit           | Screenreader können Nutzern eine sinnvoll strukturierte Seite vorlesen |
| 🧑‍💻 Wartbarkeit              | Der Code ist für Menschen leichter lesbar, verständlich und pflegbar |
| 🔄 Maschinenlesbarkeit       | APIs, Crawler und Assistenzsysteme erkennen Inhalte gezielter |
| 📱 Bessere UX auf Mobilgeräten | Kombination mit CSS & ARIA führt zu besseren mobilen Interfaces |

---

## 📄 Beispiele: Nicht-semantisch vs. semantisch

### ❌ Nicht semantisch

```html
<div class="header">...</div>
<div class="nav">...</div>
<div class="main">...</div>
```

### ✅ Semantisch korrekt

```html
<header>...</header>
<nav>...</nav>
<main>...</main>
```

---

## 🗂️ Übersicht typischer semantischer Elemente

| Element     | Zweck |
|-------------|-------|
| `<header>`  | Einleitung eines Dokuments oder Abschnitts (z. B. Logo, Navigation) |
| `<nav>`     | Navigationsmenü |
| `<main>`    | Hauptinhalt der Seite (einmal pro Seite!) |
| `<article>` | In sich geschlossener Inhalt (z. B. Blogartikel, Kommentar) |
| `<section>` | Thematisch zusammengehöriger Abschnitt |
| `<aside>`   | Randnotizen, verwandte Inhalte, Werbung |
| `<footer>`  | Abschluss oder Fußzeile eines Abschnitts oder der Seite |
| `<figure>`  | Kombination aus Bild + Beschreibung |
| `<figcaption>` | Beschreibung zu `<figure>` |
| `<mark>`    | Hervorhebung von Text, z. B. Suchtreffer |
| `<time>`    | Maschinenlesbare Zeit-/Datumsangaben |

---

## 🧠 Wann sollte man welches Element verwenden?

- **`<section>`**: Wenn es eine **eigene Überschrift (`<h2>` etc.)** enthält
- **`<article>`**: Wenn es **auch für sich alleine sinnvoll** stehen kann (z. B. Blogeintrag, News)
- **`<aside>`**: Wenn es **zusätzliche Inhalte** zum Haupttext liefert (nicht Kerninhalt)
- **`<main>`**: **Nur einmal pro Seite!** Enthält den zentralen Seiteninhalt
- **`<nav>`**: Enthält **Links zur Seitennavigation oder externen Seiten**
- **`<header>` / `<footer>`**: Können **mehrfach verwendet** werden (z. B. pro `article` oder `section`)

---

## ⚠️ Missverständnisse vermeiden

| Falsch gedacht | Richtig gedacht |
|----------------|-----------------|
| „Semantisch ist gleich SEO“ | SEO ist **ein** Vorteil, aber nicht der einzige |
| „Semantisch bedeutet hübsch“ | Semantik betrifft **Bedeutung, nicht Design** |
| „Nur `<main>` ist semantisch“ | Viele HTML5-Elemente tragen zur Semantik bei |

---

## 🛠 Best Practices

- **Vermeide reine `<div>`-Strukturen**, wenn es semantische Alternativen gibt.
- Nutze `<section>` nur mit **Überschriften** und klarer inhaltlicher Trennung.
- Verwende `<article>` nur für eigenständige Inhalte, die auch isoliert Sinn ergeben.
- Verwende **maximal ein `<main>`** pro Seite, aber **mehrere `<section>`, `<header>`, `<footer>`** innerhalb von Komponenten.

---

## 📚 Fazit

Semantisches HTML macht deine Seiten **lesbarer, zugänglicher, strukturierter** – für Menschen wie Maschinen.  
Es gehört heute zum **Standard moderner Webentwicklung** und sollte in jedem Projekt konsequent eingesetzt werden.
