# `<nav>` – Navigationsbereich

## 🧩 Funktion

Das `<nav>`-Element wird verwendet, um einen **semantisch erkennbaren Bereich für Navigationslinks** zu definieren.  
Typische Inhalte eines `<nav>`-Blocks sind:

- Hauptnavigation
- Sekundäre Navigation (z. B. Sidebar-Menü)
- Inhaltsverzeichnisse
- Paginierungen
- Breadcrumbs

> 📌 Das Element hilft **Screenreadern**, **Suchmaschinen** und **Browsern**, strukturell zwischen Navigation und Inhalt zu unterscheiden.

---

## ✅ Verwendung

```html
<nav>
  <ul>
    <li><a href="/">Startseite</a></li>
    <li><a href="/über-uns">Über uns</a></li>
    <li><a href="/kontakt">Kontakt</a></li>
  </ul>
</nav>
```

👉 Die `<nav>`-Struktur kann überall im Dokument vorkommen, sollte aber für Benutzer logisch zugänglich sein.

---

## 🔧 Attribute

| Attribut       | Beschreibung                                                 |
|----------------|--------------------------------------------------------------|
| `id`           | Für Verlinkung, Scrolling, oder JS-Zugriff                  |
| `class`        | CSS-Styling                                                  |
| `style`        | Direktes Styling (optional)                                  |
| `aria-label`   | Kurze Beschreibung für Screenreader, wenn kein sichtbarer Titel vorhanden ist |
| `aria-labelledby` | Verknüpft `<nav>` mit einem sichtbaren Titel             |

---

## 🧠 Struktur-Tipps

- Verwende `<nav>` **nur für echte Navigation**, nicht für jeden Link-Block
- Hauptnavigation **nah an den Seitenanfang** setzen
- Screenreader profitieren von **`aria-label`**, wenn der Zweck sonst nicht klar ist

---

## 🎯 Beispiel mit `aria-label`

```html
<nav aria-label="Hauptnavigation">
  <ul>
    <li><a href="/">Start</a></li>
    <li><a href="/blog">Blog</a></li>
    <li><a href="/kontakt">Kontakt</a></li>
  </ul>
</nav>
```

### Alternativ: Mit sichtbarer Überschrift

```html
<h2 id="menue">Menü</h2>
<nav aria-labelledby="menue">
  <ul>
    <li><a href="/faq">FAQ</a></li>
    <li><a href="/support">Support</a></li>
  </ul>
</nav>
```

---

## 🎨 Beispiel mit CSS

```css
nav ul {
  list-style: none;
  display: flex;
  gap: 1rem;
  padding: 0;
}

nav a {
  text-decoration: none;
  color: #0057b8;
}
```

---

## ❌ Häufige Fehler

| Fehler                                  | Korrekte Lösung                              |
|-----------------------------------------|-----------------------------------------------|
| `<nav>` ohne semantische Links         | Nur echte Navigationsbereiche einbinden      |
| Kein `aria-label` bei mehreren Navigationsleisten | Mit `aria-label` oder `aria-labelledby` ausstatten |
| Navigation als `<div>` oder `<section>` ohne Bedeutung | Besser `<nav>` mit klarer Kennzeichnung verwenden |

---

## ♿ Barrierefreiheit

- `<nav>` wird von Screenreadern als **navigierbarer Bereich** erkannt
- **Mehrere `<nav>`-Elemente** pro Seite sind erlaubt – aber jeweils **gut beschriften**
- In Kombination mit **Skip-Links** hilfreich für keyboard-only Benutzer

```html
<a href="#main" class="skip-link">Zum Inhalt springen</a>
```

---

## 🔄 Unterschied zu ähnlichen Elementen

| Element   | Zweck                                               |
|-----------|------------------------------------------------------|
| `<nav>`   | Navigation zu Seiten oder Abschnitten                |
| `<header>`| Einleitender Bereich, kann `<nav>` enthalten         |
| `<section>`| Thematische Gliederung, **nicht für Navigation**    |
| `<aside>` | Ergänzende Inhalte (z. B. Links, aber sekundär)       |

---

## 📚 Fazit

Das `<nav>`-Element gehört zu den **wichtigsten semantischen HTML5-Tags**, um Struktur, Barrierefreiheit und Usability zu verbessern.  
Verwende es bewusst für **echte Navigation** und kombiniere es mit **ARIA-Attributen**, um auch bei komplexen Seiten Klarheit zu schaffen.
