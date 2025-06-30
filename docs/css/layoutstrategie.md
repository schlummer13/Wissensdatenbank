# 🧭 CSS-Layoutstrategien – Moderne Seitenstrukturen aufbauen

## 🧩 Was sind Layoutstrategien?

Layoutstrategien beschreiben, **wie Inhalte auf einer Webseite räumlich organisiert** werden.  
Mit CSS hast du heute eine Vielzahl an Tools zur Verfügung, um einfache bis hochkomplexe Layouts flexibel und responsiv umzusetzen.

> 📌 Früher war `float` Standard – heute dominieren **Flexbox**, **Grid** und **responsive Einheiten**.

---

## 📦 Übersicht moderner Layouttechniken

| Technik       | Verwendung                                   | Besonderheiten                            |
|---------------|----------------------------------------------|--------------------------------------------|
| `display: flex` | 1-dimensionale Ausrichtung (Zeile/Spalte)    | einfach, flexibel, horizontale Strukturen  |
| `display: grid` | 2-dimensionale Rasterlayouts (Zeile + Spalte) | perfekt für komplexe Layouts               |
| `position`     | Absolute Platzierung einzelner Elemente      | gezielt, aber unflexibel für Responsive    |
| `float`        | Alte Methode zur „Seitenspalten“-Erstellung  | veraltet, schwer kontrollierbar            |
| `inline-block` | Fließende Boxen nebeneinander                | geeignet für Navigationen/Buttons          |
| Media Queries  | Reaktion auf Bildschirmgröße                 | Basis für Responsive Design                |

---

## 🔹 1. Flexbox – Layout in einer Richtung

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

- **Horizontale oder vertikale** Ausrichtung
- Gleichmäßiger Abstand, Zentrierung, Reihenfolge steuerbar
- Ideal für Navigationen, Cards, Buttonleisten

👉 Siehe auch: `flex-direction`, `flex-wrap`, `gap`, `align-self`

---

## 🔸 2. Grid – 2-dimensionale Layouts

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 1rem;
}
```

- Arbeitet mit **Zeilen UND Spalten**
- Perfekt für Seitenraster, Galerien, Layout mit Sidebar

👉 Begriffe wie `grid-template-areas`, `auto-fit`, `repeat()`, `minmax()` helfen beim Optimieren

---

## 🔸 3. Positionierung – gezielte Platzierung

```css
.element {
  position: absolute;
  top: 20px;
  right: 10px;
}
```

- Eignet sich für **Popups, Overlays, Tooltips**
- Mit `relative`-Elternelement kombinieren
- ⚠️ Nicht responsive von Natur aus

---

## 🔸 4. Float (Legacy)

```css
.sidebar {
  float: left;
  width: 30%;
}
```

- Früher für Spalten genutzt
- Muss mit `clearfix` behoben werden
- ❗ Heute nicht mehr empfohlen – besser: Flex/Grid

---

## 🔸 5. Inline-Block

```css
nav a {
  display: inline-block;
  margin-right: 1rem;
}
```

- Elemente **in einer Zeile**, aber wie Blöcke steuerbar
- Kein Zeilenumbruch wie `block`, aber `width`, `padding`, etc. möglich

---

## 🌐 6. Responsive Design mit Media Queries

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

- Anpassung an Bildschirmbreite, Höhe, Gerätetyp
- Basis für **Mobile-First-Designs**

👉 Unterstützt auch `prefers-color-scheme`, `orientation`, u.v.m.

---

## 🔧 Weitere Bausteine

| Technik             | Beschreibung                                       |
|---------------------|----------------------------------------------------|
| `gap`, `row-gap`     | Abstände zwischen Flex/Grid-Elementen             |
| `min-content`, `max-content` | Inhalte optimal dimensionieren       |
| `clamp()`            | Dynamische Größen zwischen min/max + fluid        |
| `aspect-ratio`       | Verhältnisse für responsive Medien und Container  |
| `container queries`  | Layout basierend auf **Elterngröße** *(modern)*   |

---

## 🎯 Typische Layoutmuster

| Name                  | Umsetzung                                          |
|------------------------|---------------------------------------------------|
| Header – Main – Footer | Flex/Block/Grid                                   |
| Zwei-Spalten-Layout    | Grid (`grid-template-columns: auto 1fr`)          |
| Kartenraster / Gallery | Grid + `auto-fit`, `minmax()`                     |
| Zentrierung            | Flex (`justify-content`, `align-items: center`)   |
| Sticky Header/Footer   | `position: sticky/fixed` + `z-index`              |

---

## ✅ Best Practices

- **Mobile First**: Layout für kleine Viewports, dann aufwärts erweitern
- Vermeide `float` – setze auf moderne Techniken
- Nutze `gap` statt `margin` für konsistente Abstände
- Trenne Struktur (`HTML`) und Stil (`CSS`) klar
- Verwende **Semantik + ARIA-Rollen** für Barrierefreiheit

---

## ❌ Häufige Fehler

| Fehler                         | Empfehlung                                   |
|--------------------------------|----------------------------------------------|
| Kein Responsives Layout        | Media Queries & flexible Einheiten verwenden |
| Scrollprobleme bei `position` | Kontext und `overflow` prüfen                |
| Float ohne Clear               | Besser: `flex`, sonst `clear: both` verwenden|

---

## 📚 Fazit

CSS bietet eine Vielzahl leistungsstarker **Layoutstrategien** – von einfachen Blöcken bis hin zu hochdynamischen Grid-Systemen.  
Mit **Flexbox**, **Grid** und **Media Queries** lassen sich moderne Webseiten effizient, responsiv und zugänglich gestalten.

