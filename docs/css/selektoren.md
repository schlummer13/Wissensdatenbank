# 🎯 CSS-Selektoren – Elemente gezielt ansprechen

## 🧩 Was sind Selektoren?

**Selektoren** bestimmen, **welche HTML-Elemente** durch eine CSS-Regel angesprochen und gestaltet werden.  
Sie sind das Fundament jeder Stilregel und ermöglichen sowohl einfache als auch hochkomplexe Auswahlstrukturen.

> 📌 Ein CSS-Selektor ist wie ein „Zielsystem“ – er bestimmt, **was** gestaltet wird.

---

## 🔹 Einfache Selektoren

| Typ                 | Beispiel      | Bedeutung                                |
|---------------------|---------------|-------------------------------------------|
| Element-Selektor     | `p`           | Alle `<p>`-Elemente                       |
| Klassen-Selektor     | `.highlight`  | Alle Elemente mit `class="highlight"`     |
| ID-Selektor          | `#logo`       | Das Element mit `id="logo"`               |
| Universalselektor    | `*`           | **Alle** Elemente                        |

### Beispiel:

```css
p {
  color: gray;
}

.highlight {
  background-color: yellow;
}

#logo {
  font-size: 2rem;
}
```

---

## 🔸 Kombinierte Selektoren

### 1. **Mehrere Elemente gleichzeitig**

```css
h1, h2, h3 {
  font-family: sans-serif;
}
```

### 2. **Nachbarschaft und Hierarchie**

| Selektor           | Beschreibung                                     |
|--------------------|--------------------------------------------------|
| `div p`            | Alle `<p>` innerhalb eines `<div>`               |
| `div > p`          | Nur **direkte** Kinder `<p>` von `<div>`         |
| `p + span`         | Direkt **danach** folgendes `<span>`             |
| `p ~ span`         | Alle `<span>` auf derselben Ebene nach `<p>`     |

---

## 🔹 Attribut-Selektoren

| Syntax                          | Bedeutung                                               |
|----------------------------------|----------------------------------------------------------|
| `[type]`                         | Alle Elemente mit einem `type`-Attribut                 |
| `[type="email"]`                 | Nur `type="email"`                                      |
| `[href^="https"]`                | beginnt mit `https`                                     |
| `[alt$=".png"]`                  | endet mit `.png`                                        |
| `[data-info*="produkt"]`         | enthält den Teilstring `produkt`                        |

### Beispiel:

```css
input[type="text"] {
  border: 1px solid #ccc;
}
```

---

## 🔸 Pseudo-Klassen

Sprechen **Zustände oder Positionen** von Elementen an:

| Selektor         | Beschreibung                              |
|------------------|-------------------------------------------|
| `:hover`         | Beim Überfahren mit der Maus              |
| `:focus`         | Element ist im Fokus (z. B. beim Tippen)  |
| `:first-child`   | Erstes Kindelement eines Elternteils      |
| `:last-of-type`  | Letztes Element vom gleichen Typ          |
| `:not(selector)` | Negiert andere Selektoren                 |

### Beispiel:

```css
a:hover {
  color: red;
}

ul li:first-child {
  font-weight: bold;
}
```

---

## 🔸 Pseudo-Elemente

Fügen **virtuelle Teile** zu Elementen hinzu:

| Pseudo-Element     | Funktion                                 |
|--------------------|------------------------------------------|
| `::before`         | Fügt **vor** dem Inhalt etwas hinzu      |
| `::after`          | Fügt **nach** dem Inhalt etwas hinzu     |
| `::first-letter`   | Erste Buchstabe eines Blocks             |
| `::selection`      | Markierte Textstelle                     |

### Beispiel:

```css
p::before {
  content: "🔹 ";
  color: blue;
}
```

---

## ⚖️ Spezifität und Kaskade

| Selektortyp           | Spezifität |
|------------------------|------------|
| Element                | 0,0,1      |
| Klasse                 | 0,1,0      |
| ID                     | 1,0,0      |
| Inline-Styles          | 1,0,0,0    |

Je **höher die Spezifität**, desto **"mächtiger"** die Regel bei Konflikten.

---

## ❌ Häufige Fehler

| Fehler                                | Empfehlung                                           |
|---------------------------------------|------------------------------------------------------|
| `#id.class` statt `#id .class`        | Leerzeichen beachten: selektiert **Kind, nicht Kombination** |
| `h1 h2` erwartet Hierarchie            | Nur gültig, wenn `<h2>` im `<h1>` ist                |
| `p:after` statt `p::after`            | Moderne Syntax ist **doppelt gekennzeichnet**        |

---

## 📚 Fazit

CSS-Selektoren ermöglichen gezielte, flexible und mächtige Gestaltungsmöglichkeiten.  
Vom simplen `h1` bis hin zu komplexen `[data-role^="btn"]:not(.disabled):hover` –  
**wer Selektoren beherrscht, beherrscht CSS.**