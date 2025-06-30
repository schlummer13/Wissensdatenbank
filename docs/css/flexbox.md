# 📦 CSS Flexbox – Flexibles Layoutsystem für ein-achsige Ausrichtung

## 🧩 Was ist Flexbox?

**Flexbox (Flexible Box Layout)** ist ein modernes CSS-Modul zur **dynamischen Anordnung von Elementen in einer Zeile oder Spalte**.  
Es eignet sich besonders für **Navigationen, Kartenlayouts, Ausrichtungen und Verteilungen**, ohne dass du auf komplizierte Positionierung oder Float-Tricks zurückgreifen musst.

> 📌 Flexbox = Einfaches, leistungsfähiges **1D-Layoutsystem**

---

## 📐 Grundstruktur

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  display: flex;
}
```

- **Elternelement** erhält `display: flex`
- **Kind-Elemente** werden automatisch **nebeneinander** dargestellt (horizontal)

---

## 🔧 Hauptachsen & Begriffe

| Achse                | Bedeutung                          |
|----------------------|-------------------------------------|
| Hauptachse (main)    | Standard: horizontal (row)         |
| Kreuzachse (cross)   | Standard: vertikal                 |
| Flex-Container       | Das Element mit `display: flex`    |
| Flex-Items           | Alle direkten Kinder des Containers |

---

## 🔹 Container-Eigenschaften

### `flex-direction`

Bestimmt die Richtung der Hauptachse:

```css
flex-direction: row;        /* (default) horizontal von links nach rechts */
flex-direction: row-reverse;
flex-direction: column;     /* vertikal von oben nach unten */
flex-direction: column-reverse;
```

---

### `flex-wrap`

Erlaubt das Umbrechen von Elementen:

```css
flex-wrap: nowrap;         /* (default) alles in einer Zeile */
flex-wrap: wrap;           /* bricht auf nächste Zeile/Spalte um */
flex-wrap: wrap-reverse;
```

---

### `justify-content`

Verteilt Flex-Items entlang der Hauptachse:

```css
justify-content: flex-start;    /* (default) linksbündig */
justify-content: flex-end;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
```

---

### `align-items`

Ausrichtung entlang der **Kreuzachse**:

```css
align-items: stretch;       /* (default) füllt Höhe */
align-items: flex-start;
align-items: flex-end;
align-items: center;
align-items: baseline;
```

---

### `align-content`

Nur bei **mehrzeiligen Layouts** wirksam (wenn `flex-wrap: wrap`):

```css
align-content: flex-start;
align-content: center;
align-content: space-between;
```

---

## 🔸 Item-Eigenschaften

### `flex-grow`

Verteilt **übrigen Platz** unter Items:

```css
.item {
  flex-grow: 1; /* wächst gleichmäßig mit */
}
```

### `flex-shrink`

Bestimmt, **wie stark Elemente schrumpfen dürfen**:

```css
.item {
  flex-shrink: 1;
}
```

### `flex-basis`

**Startgröße**, ähnlich `width`/`height`, vor Verteilung des Rests:

```css
.item {
  flex-basis: 200px;
}
```

### Kurzform: `flex`

```css
.item {
  flex: 1 1 200px; /* grow shrink basis */
}
```

---

### `align-self`

Einzelne Items individuell ausrichten (Kreuzachse):

```css
.item {
  align-self: flex-end;
}
```

---

## 🎯 Praxisbeispiel: 3-spaltige Verteilung

```css
.container {
  display: flex;
  gap: 1rem;
}

.item {
  flex: 1;
  background: #eee;
  padding: 1rem;
}
```

---

## 🧪 Zentrierung mit Flexbox

```css
.centered {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
```

✅ Sehr einfache vertikale UND horizontale Zentrierung

---

## 💡 Nützliche Tipps

| Ziel                            | Eigenschaft                      |
|----------------------------------|----------------------------------|
| Horizontales Menü               | `flex-direction: row`            |
| Spaltenlayout                   | `flex-direction: column`         |
| Gleich hohe Karten              | `align-items: stretch`           |
| Lücke zwischen Items            | `gap: 1rem;`                     |
| Abstand zwischen Blöcken        | `margin`/`space-between` kombinieren |

---

## ❌ Häufige Fehler

| Fehler                          | Ursache                                      |
|----------------------------------|----------------------------------------------|
| `align-items` wirkt nicht        | Nur sichtbar bei unterschiedlich hoher Höhe  |
| `justify-content` funktioniert nicht | Flex-Container nicht korrekt definiert     |
| Keine Umbrüche                  | `flex-wrap` fehlt                            |

---

## 📚 Fazit

**Flexbox** ist das perfekte Werkzeug für **1-dimensionale Layouts** – sei es horizontal oder vertikal.  
Es ersetzt alte Techniken wie `float`, `inline-block` und manuelle Berechnungen.
