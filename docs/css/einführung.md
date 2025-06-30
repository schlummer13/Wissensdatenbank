# 🎨 Einführung in CSS – Cascading Style Sheets

## 🧩 Was ist CSS?

**CSS** steht für **Cascading Style Sheets** (auf Deutsch: *gestufte Stilvorlagen*) und ist die Sprache zur Gestaltung von HTML-Dokumenten.  
Während HTML die **Struktur** und den **Inhalt** einer Webseite beschreibt, ist CSS dafür zuständig, **Aussehen, Layout und visuelles Verhalten** festzulegen.

> 📌 **Trennung von Struktur und Design** ist ein zentrales Webentwicklungsprinzip:  
> - **HTML** = Was ist da?  
> - **CSS** = Wie sieht es aus?

---

## 📦 Was kann CSS?

CSS steuert z. B.:

- Farben (`color`, `background`)
- Schriftarten und Größen (`font-family`, `font-size`)
- Abstände (`margin`, `padding`)
- Layouts (`flex`, `grid`)
- Animationen und Übergänge
- Sichtbarkeit und Zustände
- Responsives Design für Mobilgeräte

---

## 🔗 CSS in HTML einbinden

### 1. 📄 Externe Datei (empfohlen)

```html
<link rel="stylesheet" href="style.css" />
```

### 2. 🧩 Intern im `<head>`

```html
<style>
  body {
    background-color: #f0f0f0;
  }
</style>
```

### 3. ✏️ Inline im Element (nicht empfohlen)

```html
<p style="color: red;">Dieser Text ist rot.</p>
```

---

## 🧠 Aufbau einer CSS-Regel

```css
selector {
  eigenschaft: wert;
}
```

Beispiel:

```css
h1 {
  color: blue;
  font-size: 2rem;
}
```

| Teil        | Bedeutung                                   |
|-------------|----------------------------------------------|
| `selector`  | Welches Element soll gestaltet werden?       |
| `property`  | Was soll verändert werden (z. B. Farbe)?      |
| `value`     | Wie genau (z. B. rot, 100px)?                 |

---

## 📚 Beispiel: HTML + CSS

```html
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <title>Meine erste CSS-Seite</title>
  <style>
    body {
      background-color: #fffbe6;
      font-family: sans-serif;
    }

    h1 {
      color: #2a7ae2;
    }

    p {
      font-size: 1.1rem;
    }
  </style>
</head>
<body>
  <h1>Hallo CSS!</h1>
  <p>Das ist ein formatiertes HTML-Dokument mit eingebettetem CSS.</p>
</body>
</html>
```

---

## 🧱 CSS-Konzepte im Überblick

| Thema                  | Beschreibung                                               |
|------------------------|------------------------------------------------------------|
| Selektoren             | Wählen HTML-Elemente aus (`h1`, `.klasse`, `#id`)          |
| Farben & Einheiten     | Farbcodes (`#fff`, `rgb()`, `hsl()`), Größen in `px`, `em` |
| Box-Modell             | Layoutmodell mit `margin`, `border`, `padding`, `content` |
| Positionierung         | `static`, `relative`, `absolute`, `fixed`, `sticky`       |
| Flexbox & Grid         | Moderne Layoutsysteme für flexible Designs                |
| Pseudo-Klassen         | z. B. `:hover`, `:first-child`, `:nth-of-type()`           |
| Animationen & Effekte  | Mit `@keyframes`, `transition`, `transform`, `opacity`    |
| Medienabfragen         | `@media` für Responsive Design                            |
| Variablen              | `--main-color: #333;` und `var(--main-color)`             |
| Spezifität & Vererbung | Wer überschreibt wen? Kaskade & Priorität verstehen       |

---

## 🔄 Vorteile von CSS

✅ Trennung von Inhalt und Gestaltung  
✅ Wiederverwendbarkeit über mehrere Seiten  
✅ Schnellere Ladezeiten (bei externer Datei)  
✅ Verbesserte Wartbarkeit und Übersichtlichkeit  
✅ Erforderlich für modernes Responsive Webdesign  

---

## ⚠️ Wichtige Begriffe

- **Kaskade**: Die Reihenfolge und Gewichtung von CSS-Regeln
- **Vererbung**: Viele Eigenschaften vererben sich an Kind-Elemente
- **Spezifität**: Je präziser ein Selektor, desto "wichtiger" seine Regel
- **!important**: Erzwingt eine Regel – aber nur als Notlösung verwenden

---

## 📚 Fazit

CSS ist das Herzstück jeder modernen Webgestaltung.  
Es verleiht Webseiten ihren Look, ermöglicht responsives Verhalten auf allen Geräten und ist ein Muss für eine gute Nutzererfahrung.