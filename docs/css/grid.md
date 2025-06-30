# 🧮 CSS Grid – Zweidimensionales Layoutsystem

## 🧩 Was ist CSS Grid?

**CSS Grid Layout** ist ein leistungsstarkes, **zweidimensionales Layoutsystem** für das Web.  
Im Gegensatz zu Flexbox (nur Zeile ODER Spalte) erlaubt Grid die **gleichzeitige Gestaltung von Reihen und Spalten** – perfekt für komplexe, responsive Layouts.

> 📌 Ideal für **Seitenlayouts, Raster, Galerien, Dashboards, Karten-Grids**

---

## 📐 Grundstruktur

```html
<div class="grid">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

```css
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 1rem;
}
```

- `display: grid` aktiviert Grid-Modus
- `grid-template-columns` definiert Spalten (hier: drei gleich große)

---

## 🔧 Zentrale Eigenschaften

### `grid-template-columns` / `grid-template-rows`

Definiert die Spalten- und Zeilenstruktur.

```css
grid-template-columns: 200px 1fr 2fr;
grid-template-rows: auto 100px;
```

| Wert        | Bedeutung                           |
|-------------|--------------------------------------|
| `px`/`em`   | Feste Breite/Höhe                   |
| `%`         | Prozentanteil am Container          |
| `fr`        | Anteil am **freien Platz**          |
| `auto`      | So groß wie der Inhalt               |

---

### `gap` (Abstand)

```css
gap: 1rem;
row-gap: 2rem;
column-gap: 0.5rem;
```

---

### `repeat()` – Wiederholungen

```css
grid-template-columns: repeat(3, 1fr); /* 3 gleich breite Spalten */
```

---

### `minmax()` – flexible Begrenzung

```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

- Dynamische Spalten, mind. 200px breit, maximal verfügbarer Platz

---

## 🔹 Platzierung von Elementen

### Automatisch

Elemente werden **automatisch** in das Raster eingefügt – Zeile für Zeile.

### Manuell mit `grid-column`, `grid-row`

```css
.item {
  grid-column: 1 / 3; /* von Spalte 1 bis 3 */
  grid-row: 2 / 4;
}
```

---

### Kurzform: `grid-area`

```css
grid-area: 2 / 1 / 3 / 4; /* row-start / column-start / row-end / column-end */
```

---

## 🧭 Grid Areas – benannte Bereiche

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "nav    main"
    "footer footer";
  grid-template-columns: 1fr 3fr;
  grid-template-rows: auto 1fr auto;
}
```

```css
.header { grid-area: header; }
.nav    { grid-area: nav; }
.main   { grid-area: main; }
.footer { grid-area: footer; }
```

📌 **Vorteil**: Semantisches, visuelles Layout

---

## 🔄 Automatische Platzierung

### `grid-auto-flow`

```css
grid-auto-flow: row;       /* Standard: Zeilenweise */
grid-auto-flow: column;    /* Spaltenweise */
```

---

## 🌐 Responsive Grid

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
}
```

✅ Passt die Anzahl der Spalten **dynamisch** an die Breite an  
✅ Perfekt für Galerien, Cards, Listen

---

## 🎯 Beispiel: 3×2 Grid

```css
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 100px 100px;
  gap: 10px;
}
```

```html
<div class="grid">
  <div>1</div><div>2</div><div>3</div>
  <div>4</div><div>5</div><div>6</div>
</div>
```

---

## ✅ Best Practices

| Tipp                               | Vorteil                                   |
|------------------------------------|-------------------------------------------|
| Verwende `fr` statt `px`           | Flexibler, besser für Responsive Design   |
| Nutze `auto-fit` + `minmax()`      | Automatische Spaltenanzahl                |
| Benenne Grid Areas (`grid-area`)   | Klarheit im Code                          |
| Verwende `gap` statt `margin`      | Einheitlich und sicher                    |

---

## ❌ Häufige Fehler

| Problem                           | Ursache / Lösung                          |
|-----------------------------------|-------------------------------------------|
| Elemente überlappen sich          | Fehlerhafte `grid-column` / `row` Werte   |
| Kein Platz im Layout              | Container hat keine definierte Breite     |
| Unterschiedlich hohe Spalten      | `align-items: stretch` setzen             |

---

## 📚 Fazit

**CSS Grid** ist das ideale Werkzeug für strukturierte, responsive, zweidimensionale Layouts.  
Es ist leistungsfähiger und klarer als frühere Methoden wie Tabellen oder `float`-basierte Layouts.
