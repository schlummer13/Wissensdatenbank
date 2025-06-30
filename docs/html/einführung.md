# Was ist HTML?

**HTML** steht für **HyperText Markup Language** und ist die standardisierte Auszeichnungssprache zur **Strukturierung von Inhalten im Web**. Sie bildet das **Grundgerüst jeder Webseite** und definiert, **welche Inhalte** auf einer Seite stehen und **wie sie strukturiert** sind – zum Beispiel Überschriften, Absätze, Bilder oder Links.

HTML allein erzeugt jedoch **keine optisch ansprechende oder interaktive Webseite** – dafür werden **CSS** (Cascading Style Sheets) für das Design und **JavaScript** für dynamisches Verhalten verwendet.

---

## 🧱 Grundidee von HTML

HTML basiert auf sogenannten **Tags** (dt. "Markierungen"). Diese bestehen aus einem öffnenden und einem schließenden Element, z. B.:

```html
<p>Dies ist ein Absatz</p>
```

Das `<p>` ist ein Absatz-Tag. Es signalisiert dem Browser, dass es sich bei dem Inhalt um einen Absatz handelt. Es gibt Tags für viele verschiedene Zwecke:

- `<h1>` bis `<h6>` – Überschriften  
- `<a>` – Links  
- `<img>` – Bilder  
- `<ul>` / `<li>` – Listen  
- `<form>` / `<input>` – Formulare  
- `<div>` und `<span>` – Layout und Gruppierung  
- und viele mehr.

Tags können auch **Attribute** enthalten, die zusätzliche Informationen bereitstellen:

```html
<img src="bild.jpg" alt="Beispielbild" width="200" />
```

- `src` gibt die Bildquelle an  
- `alt` liefert eine Beschreibung (wichtig für Barrierefreiheit)  
- `width` definiert die Breite in Pixeln

---

## 🕰️ Kurze Geschichte von HTML

### 1989–1990 – Die Geburt des Web

HTML wurde Ende der 1980er/Anfang der 1990er von **Tim Berners-Lee**, einem Physiker am CERN, entwickelt. Sein Ziel war es, ein System zu schaffen, mit dem Wissenschaftler Dokumente einfach miteinander teilen konnten. Daraus entstand das World Wide Web.

👉 Das erste HTML-Dokument entstand 1991.

### 1993 – HTML wird öffentlich

Das erste veröffentlichte HTML-Spezifikationsdokument war der sogenannte **HTML Tags Guide** von 1993. Damals gab es nur 18 Tags.

### Mitte 1990er – Browserkrieg und Chaos

Mit dem Aufkommen von Netscape und Internet Explorer entstand ein „Browserkrieg“. Beide Firmen fügten eigene HTML-Erweiterungen hinzu, was zu **Kompatibilitätsproblemen** führte.

### 1997 – W3C übernimmt

Das **World Wide Web Consortium (W3C)** übernahm die Standardisierung und veröffentlichte HTML 4.01 im Jahr 1999. Es war der erste große Versuch, Ordnung in die vielen Varianten zu bringen.

### 2008–2014 – HTML5 kommt

HTML5 wurde über Jahre entwickelt und 2014 offiziell abgeschlossen. Es brachte viele moderne Funktionen mit:

- Native Audio-/Video-Unterstützung  
- `<canvas>` für Grafik  
- Semantische Elemente wie `<article>`, `<section>`, `<nav>`  
- Offline-Support (z. B. durch Service Worker)

📌 **Hinweis:** HTML5 wird heute als sogenannter *Living Standard* vom **WHATWG** (Web Hypertext Application Technology Working Group) weiterentwickelt – es bleibt also nie „stehen“.

---

## 📋 Wichtige Eigenschaften

- **Textbasiert** und leicht zu lernen  
- **Semantisch**, d. h. es beschreibt die Bedeutung der Inhalte  
- **Plattformunabhängig** und läuft in jedem modernen Browser  
- Funktioniert ideal in Kombination mit **CSS** und **JavaScript**  
- Grundlage moderner Webentwicklung

📌 **Zusatzwissen**: Wenn HTML-Tags fehlen oder falsch verschachtelt sind, versuchen Browser dennoch, die Seite möglichst sinnvoll darzustellen – das nennt man **Fehlertoleranz**.

---

## 📄 Beispiel: Mini-Webseite

```html
<!DOCTYPE html>
<html lang="de">
  <head>
    <meta charset="UTF-8" />
    <title>Meine erste HTML-Seite</title>
  </head>
  <body>
    <h1>Hallo Welt!</h1>
    <p>Dies ist meine erste Webseite mit HTML.</p>
    <a href="https://example.com">Mehr erfahren</a>
  </body>
</html>
```

👨‍💻 Du kannst HTML direkt im Browser testen oder Tools wie **Visual Studio Code**, **JSFiddle** oder **CodePen** nutzen.

---

## 🔍 Bonus: HTML-Code prüfen

Verwende den offiziellen **[W3C Markup Validator](https://validator.w3.org/)**, um deinen HTML-Code auf Fehler zu überprüfen und saubere, gültige Webseiten zu erstellen.

---

## 📚 Fazit

HTML ist das **Rückgrat des Internets**. Ohne HTML gäbe es keine Webseiten, keine Blogs, keine Online-Shops. Auch wenn es auf den ersten Blick simpel wirkt, ist es die Grundlage für alles, was im Web passiert.

✨ Wer Webseiten bauen möchte, kommt an HTML nicht vorbei – es ist das **Fundament jeder digitalen Präsenz**.