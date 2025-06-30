# `<ul>`, `<ol>`, `<li>` – Listen in HTML

## 🧩 Funktion

HTML bietet zwei Arten von strukturierten Listen:

- `<ul>` – **Ungeordnete Liste**: Punkte ohne Reihenfolge (Bullet Points)
- `<ol>` – **Geordnete Liste**: Punkte in nummerierter Reihenfolge
- `<li>` – **Listenelement**: Ein Eintrag in einer Liste, sowohl in `<ul>` als auch `<ol>`

> 📌 Listen verbessern die **Lesbarkeit, Struktur und Zugänglichkeit** von Inhalten – sowohl für Menschen als auch für Suchmaschinen.

---

## ✅ Verwendung

### Ungeordnete Liste (`<ul>`)

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

👉 Wird typischerweise für Aufzählungen ohne feste Reihenfolge genutzt.

### Geordnete Liste (`<ol>`)

```html
<ol>
  <li>Vorbereitung</li>
  <li>Programmieren</li>
  <li>Testen</li>
</ol>
```

👉 Ideal für Schritt-für-Schritt-Anleitungen oder priorisierte Inhalte.

---

## 🔧 Attribute

### `<ol>`

| Attribut | Beschreibung                                           |
|----------|--------------------------------------------------------|
| `type`   | Art der Nummerierung: `1`, `a`, `A`, `i`, `I`          |
| `start`  | Startwert der Nummerierung (z. B. `start="3"`)         |
| `reversed` | Kehrt die Reihenfolge um (z. B. 5, 4, 3, ...)        |

### `<ul>`

| Attribut | Beschreibung                             |
|----------|------------------------------------------|
| `type` (veraltet) | Bullet-Stil (nicht mehr empfohlen) |

### `<li>`

| Attribut | Beschreibung                             |
|----------|------------------------------------------|
| `value`  | Eigene Nummerierung (nur in `<ol>`)      |
| `class`, `id`, `style` | Für individuelles Styling  |

---

## 🎨 Beispiel mit CSS

```html
<ul class="skills">
  <li>Python</li>
  <li>SQL</li>
  <li>Scraping</li>
</ul>
```

```css
.skills {
  list-style-type: square;
  padding-left: 1.5rem;
}

.skills li {
  margin-bottom: 0.5rem;
}
```

---

## 🧠 Erweiterte Varianten

### Verschachtelte Listen

```html
<ul>
  <li>Frontend
    <ul>
      <li>HTML</li>
      <li>CSS</li>
    </ul>
  </li>
  <li>Backend
    <ul>
      <li>Python</li>
      <li>Node.js</li>
    </ul>
  </li>
</ul>
```

👉 Gut geeignet für hierarchische Inhalte (z. B. Themenbäume, Navigationen)

### Kombination mit `<nav>`

```html
<nav>
  <ul>
    <li><a href="/">Start</a></li>
    <li><a href="/blog">Blog</a></li>
    <li><a href="/kontakt">Kontakt</a></li>
  </ul>
</nav>
```

👉 Ideal für Menüstrukturen in Navigationen

---

## ♿ Barrierefreiheit

- Listen sind **von Natur aus zugänglich**
- `<ol>` signalisiert Screenreadern die **Reihenfolge der Schritte**
- `<ul>` signalisiert nur Aufzählung, ohne Reihenfolge
- Bullet-Styles sollten nicht allein zur Bedeutung verwendet werden

---

## ❌ Häufige Fehler

| Fehler                                     | Besser                                       |
|--------------------------------------------|----------------------------------------------|
| Listen ohne `<ul>` oder `<ol>` verwendet   | Semantische Tags unbedingt verwenden         |
| Inline-Listen ohne Sinn                    | Lieber als Fließtext oder Tabelle darstellen |
| Nur mit `<br>` anstatt `<li>` getrennt     | Struktur immer mit `<li>` aufbauen           |

---

## 🔄 Vergleich: `<ul>` vs. `<ol>`

| Kriterium      | `<ul>` – ungeordnet        | `<ol>` – geordnet              |
|----------------|-----------------------------|--------------------------------|
| Reihenfolge    | Nicht wichtig               | Wichtig / nummeriert           |
| Standardstil   | Bullet Points               | Zahlen (1, 2, 3, ...)          |
| Verwendung     | Menüs, Features, Inhalte    | Anleitungen, Prozesse, Rankings |

---

## 📚 Fazit

Listen sind ein zentrales Werkzeug in HTML zur **klaren Strukturierung von Inhalten**.  
Ob für Anleitungen, Navigationsmenüs oder thematische Gliederung: Mit `<ul>`, `<ol>` und `<li>` lassen sich Inhalte semantisch und visuell übersichtlich aufbereiten.
