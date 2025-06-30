# 🧱 `display` – Anzeigeverhalten von Elementen

## 🧩 Was ist `display`?

Die CSS-Eigenschaft `display` legt fest, **wie ein HTML-Element im Layout dargestellt wird** – ob als Block, inline, Flex-Container oder sogar unsichtbar.  
Sie ist **eine der grundlegendsten CSS-Eigenschaften**, da sie das Verhalten und die Struktur des Layouts maßgeblich beeinflusst.

---

## 🔍 Übersicht wichtiger Display-Typen

| Wert           | Beschreibung                                                              |
|----------------|---------------------------------------------------------------------------|
| `block`        | Element beginnt in neuer Zeile, nimmt gesamte Breite ein (`<div>`, `<p>`) |
| `inline`       | Kein Zeilenumbruch, nur so breit wie nötig (`<span>`, `<a>`)              |
| `inline-block` | Wie `inline`, aber mit einstellbarer Breite/Höhe                          |
| `none`         | Element wird **nicht gerendert**                                          |
| `flex`         | Aktiviert Flexbox-Layout für Kind-Elemente                                |
| `inline-flex`  | Wie `flex`, aber bleibt im Inline-Kontext                                 |
| `grid`         | Aktiviert Grid-Layout für Kind-Elemente                                   |
| `inline-grid`  | Wie `grid`, aber inline                                                    |
| `contents`     | Entfernt Box, aber **lässt Kind-Elemente bestehen**                       |
| `table`        | Simuliert Verhalten wie bei HTML-Tabellen                                 |

---

## 🧱 Block vs. Inline

### 🟥 `display: block`

- Beginnt **immer auf neuer Zeile**
- Nimmt **volle Breite** ein
- Höhe, Breite, Margin & Padding anwendbar

```css
div {
  display: block;
}
```

### 🟦 `display: inline`

- Läuft im **Fließtext**
- Nimmt **nur so viel Breite wie nötig**
- **Höhe und Breite ignoriert**

```css
span {
  display: inline;
}
```

---

## 🟪 `display: inline-block`

- Hybrid: **inline**-Verhalten, aber mit **Block-Eigenschaften**
- Breite, Höhe, Padding und Margin möglich

```css
button {
  display: inline-block;
  width: 200px;
}
```

---

## 🚫 `display: none`

- Element wird **komplett entfernt**
- Kein Platzverbrauch im Layout
- Nicht sichtbar, **nicht erreichbar für Screenreader**

```css
.modal {
  display: none;
}
```

👉 Alternative: `visibility: hidden` (unsichtbar, aber nimmt Platz ein)

---

## 🧰 Moderne Layouts: `flex` und `grid`

### 🔹 `display: flex`

- Aktiviert **Flexbox-Modell**  
- Kind-Elemente können flexibel ausgerichtet und verteilt werden

```css
.container {
  display: flex;
  justify-content: space-between;
}
```

### 🔹 `display: grid`

- Aktiviert **CSS Grid Layout**
- Ideal für zweidimensionale Strukturen

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr;
}
```

---

## 🧪 Spezialfälle

### 🔸 `contents`

- Das Element **selbst verschwindet**
- Seine Kinder erscheinen **direkt auf Elternebene**

```css
.wrapper {
  display: contents;
}
```

> ⚠️ Barrierefreiheit & DOM-Semantik können leiden. Mit Vorsicht verwenden!

### 🔸 `table`, `table-row`, `table-cell`

- Simulation von Tabellenelementen ohne `<table>`

```css
.container {
  display: table;
}
.row {
  display: table-row;
}
.cell {
  display: table-cell;
}
```

---

## ❌ Häufige Fehler

| Problem                               | Lösung                                                  |
|---------------------------------------|----------------------------------------------------------|
| Breite/Höhe funktioniert nicht        | `inline` → besser: `inline-block`                       |
| Element „verschwindet“                | `display: none` vs. `visibility: hidden` unterscheiden  |
| Flex/Grid funktioniert nicht          | Eltern brauchen `display: flex` / `grid`                |
| `display: contents` → Styles gehen verloren | Prüfen, ob Selektoren/Vererbungen greifen           |

---

## 👁️ Vergleich: Sichtbarkeit vs. Display

| Eigenschaft       | Verhalten                     | Platzverbrauch | Zugriff durch Screenreader |
|-------------------|-------------------------------|----------------|-----------------------------|
| `display: none`   | Unsichtbar & **aus DOM-Layout** | ❌ Nein        | ❌ Nein                     |
| `visibility: hidden` | Unsichtbar, **bleibt im Layout** | ✅ Ja      | ✅ Ja (aber nicht fokussierbar) |

---

## 📚 Fazit

Die Wahl des `display`-Werts bestimmt, wie sich ein Element im Layout verhält.  
Ob einfache Struktur mit `block`, Inline-Inhalte oder moderne Flexbox-/Grid-Systeme –  
**`display` ist die Grundlage für jedes CSS-Layout**.
