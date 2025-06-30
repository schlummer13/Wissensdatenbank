# `<style>` – CSS direkt im HTML-Dokument

## 🧩 Funktion

Das `<style>`-Element wird verwendet, um **CSS-Code direkt in ein HTML-Dokument einzubetten**. Es definiert **Gestaltungsregeln für das Aussehen der Webseite**, z. B. Farben, Schriftarten, Abstände und Layout.

Es befindet sich typischerweise im `<head>`-Bereich der Seite und wirkt sich auf alle passenden Elemente im Dokument aus.

---

## ✅ Grundverwendung

```html
<head>
  <style>
    body {
      background-color: #f2f2f2;
      font-family: Arial, sans-serif;
    }

    h1 {
      color: darkblue;
      text-align: center;
    }
  </style>
</head>
```

**Was passiert?**  
👉 Der Hintergrund der Seite wird grau, die Schriftart auf Arial gesetzt, und alle `<h1>`-Elemente werden blau und zentriert angezeigt.

---

## 🔧 Wichtige Attribute

| Attribut | Beschreibung |
|----------|--------------|
| `type`   | MIME-Type des Inhalts – `text/css` *(veraltet, optional)* |
| `media`  | Zielmedium – z. B. `screen`, `print`, `all` |
| `scoped`| Begrenzung des Styles auf ein Elternelement (nicht standardisiert) |

### Beispiel mit `media`:

```html
<style media="print">
  body {
    color: black;
    background: white;
  }
</style>
```

👉 Wird nur angewendet, wenn die Seite **gedruckt** wird.

---

## 🧪 Beispiele

### 1. 🎨 Einfache globale Gestaltung

```html
<style>
  p {
    line-height: 1.6;
    font-size: 1.1rem;
  }

  a {
    color: #0077cc;
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }
</style>
```

### 2. 📱 Media Queries

```html
<style>
  body {
    font-size: 16px;
  }

  @media (max-width: 600px) {
    body {
      font-size: 14px;
    }
  }
</style>
```

👉 Passt die Schriftgröße auf kleineren Bildschirmen an.

---

## 🚫 Nachteile von `<style>` im Vergleich zu externer CSS-Datei

| Problem | Erklärung |
|--------|-----------|
| Schwer wiederverwendbar | Styles sind auf ein einzelnes Dokument beschränkt |
| Redundanz | Mehrere Seiten mit eingebettetem CSS erhöhen die Dateigröße |
| Wartung | Änderungen müssen in jeder Datei einzeln gemacht werden |
| Caching | Externe CSS-Dateien können vom Browser zwischengespeichert werden – eingebettete nicht |

---

## 📦 Alternativen

| Methode                | Vorteile |
|------------------------|----------|
| `<link rel="stylesheet">` | Externe CSS-Datei, wiederverwendbar, wartbar |
| Inline-CSS (`style="..."`) | Für Einzelanpassungen direkt im Tag (nicht empfohlen für größere Projekte) |

---

## 🔒 Sicherheit

- Das `<style>`-Tag selbst ist sicher, **solange es nicht mit Benutzereingaben manipuliert wird**.
- Niemals benutzerdefinierte Inhalte ungefiltert in `<style>`-Tags einsetzen.
- Bei dynamischer CSS-Erzeugung in JavaScript unbedingt auf **XSS-Schutz** achten!

---

## 🔥 Best Practices

- Verwende `<style>` nur für kleine oder seiten-spezifische Stile.
- Größere Projekte sollten mit **externen Stylesheets** (`<link>`) arbeiten.
- Halte CSS getrennt von Struktur (HTML) und Verhalten (JS) – das erhöht Wartbarkeit und Klarheit.
- Nutze `media`-Attribute, wenn du spezifische Styles für Druck oder Mobilgeräte brauchst.

---

## ♿ Barrierefreiheit

- Achte auf ausreichende Kontraste (`color` vs. `background-color`)
- Vermeide Layouts, die ausschließlich auf Farben oder visuelle Effekte setzen.
- Verwende relative Einheiten (`em`, `rem`, `%`) statt fester Pixelgrößen – das erleichtert Zoom und Lesbarkeit.

---

## 📚 Fazit

Das `<style>`-Element erlaubt dir, direkt im HTML-Dokument **CSS-Regeln zu definieren**. Für kleinere Projekte oder Prototypen ist es praktisch – für größere Webseiten solltest du auf externe Stylesheets setzen, um saubere Trennung von Layout und Inhalt zu gewährleisten.
