# Einführung in HTML-Tags

Der grundlegende Baustein von HTML sind sogenannte **Tags**.

---

## 🏷️ Was ist ein HTML-Tag?

Ein **HTML-Tag** ist ein Code-Element, das einem Webbrowser mitteilt, wie Inhalte dargestellt werden sollen.

Beispiel für ein Tag mit Inhalt:

```html
<p>Dies ist ein Absatz.</p>
```

- `<p>` ist der **Start-Tag**.
- `</p>` ist der **End-Tag**.
- Der Text dazwischen ist der **Inhalt**.

**Selbstschließende Tags** benötigen keinen End-Tag:

```html
<img src="bild.jpg" alt="Ein Bild" />
<br />
```

---

## 🎯 Wofür werden HTML-Tags verwendet?

HTML-Tags geben Struktur und Bedeutung für:

- **Texte**: Überschriften, Absätze, Listen
- **Medien**: Bilder, Videos, Audiodateien
- **Links**: Navigation zwischen Seiten
- **Formulare**: Eingabefelder, Buttons, Auswahlmenüs
- **Layout**: Container und semantische Struktur

---

## 🧩 Attribute in HTML-Tags

Tags können durch **Attribute** zusätzliche Informationen enthalten.

### Syntax:

```html
<tagname attribut="wert">Inhalt</tagname>
```

Beispiel:

```html
<a href="https://example.com" target="_blank">Zur Seite</a>
```

### Häufige Attribute:

| Attribut   | Bedeutung                                      |
|------------|------------------------------------------------|
| `id`       | Einzigartige Kennung                          |
| `class`    | CSS-Klasse(n) für Styling und JS              |
| `style`    | Inline-CSS                                    |
| `title`    | Tooltip-Text beim Hover                       |
| `href`     | Linkziel bei `<a>`                            |
| `src`      | Quelle (z. B. bei Bildern, Videos)            |
| `alt`      | Alternativtext bei Bildern                    |
| `type`     | Typ (z. B. bei Inputs oder Buttons)           |
| `name`     | Name von Formularelementen                    |
| `value`    | Vorgabewert oder aktueller Wert               |
| `target`   | Ziel-Fenster (`_blank`, `_self` etc.)         |

---

## 🔝 Gängige HTML-Tags im Überblick

### 1. **Textstrukturierung**

```html
<h1>Hauptüberschrift</h1>
<h2>Unterüberschrift</h2>
<p>Ein normaler Absatztext.</p>
<br /> <!-- Zeilenumbruch -->
<hr /> <!-- Trennlinie -->
```

### 2. **Verlinkung**

```html
<a href="https://example.com" target="_blank">Externer Link</a>
```

### 3. **Bilder und Medien**

```html
<img src="bild.jpg" alt="Ein schönes Bild" />

<video controls>
  <source src="video.mp4" type="video/mp4" />
</video>
```

### 4. **Listen**

```html
<ul>
  <li>Listenpunkt A</li>
  <li>Listenpunkt B</li>
</ul>

<ol>
  <li>Erster Punkt</li>
  <li>Zweiter Punkt</li>
</ol>
```

### 5. **Container & Semantik**

```html
<div class="wrapper">Blockelement für Layout</div>
<span class="label">Inline-Element</span>

<header>Kopfbereich</header>
<footer>Fußbereich</footer>
<main>Hauptinhalt</main>
<article>Artikel</article>
<section>Abschnitt</section>
<nav>Navigation</nav>
```

### 6. **Formulare**

```html
<form action="/submit" method="post">
  <label for="email">E-Mail:</label>
  <input type="email" id="email" name="user_email" />
  <button type="submit">Absenden</button>
</form>
```

---

## ✅ Tipps für gute HTML-Nutzung

- **Immer schließen**: Verwende immer passende End-Tags.
- **Semantik beachten**: Nutze `<header>`, `<main>`, `<footer>` für besseren Code und bessere SEO.
- **Zugänglichkeit**: Verwende `alt`-Attribute für Bilder und sprechende `label`-Texte für Eingabefelder.
