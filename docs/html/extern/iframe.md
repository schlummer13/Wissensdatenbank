# `<iframe>` – Externe Inhalte einbetten

## 🧩 Funktion

Das `<iframe>`-Element (Inline Frame) ermöglicht es, **eine andere HTML-Seite oder Ressource in das aktuelle Dokument einzubetten**. Es wird häufig genutzt für:

- YouTube-Videos
- Karten (z. B. Google Maps)
- Externe Inhalte oder Tools
- Vorschauen auf andere Webseiten

> 📌 `<iframe>` lädt eine **eigene HTML-Seite** in einem definierten Bereich innerhalb der aktuellen Seite.

---

## ✅ Grundverwendung

```html
<iframe src="https://example.com" width="800" height="600" title="Externe Website">
  <p>Ihr Browser unterstützt keine eingebetteten Inhalte.</p>
</iframe>
```

- `src` gibt die eingebettete Ressource an
- `title` ist wichtig für die Barrierefreiheit
- `width` und `height` steuern die Größe
- Fallback-Text wird angezeigt, wenn das Element nicht geladen werden kann

---

## 🔧 Attribute im Überblick

| Attribut      | Beschreibung                                               |
|---------------|------------------------------------------------------------|
| `src`         | URL der eingebetteten Seite oder Ressource                |
| `title`       | **Barrierefreie Beschreibung** des eingebetteten Inhalts  |
| `width`, `height` | Größe des Iframes in Pixel                            |
| `allowfullscreen` | Erlaubt Vollbildmodus (z. B. für Videos)             |
| `loading`     | `lazy` für verzögertes Laden                              |
| `sandbox`     | Aktiviert Sicherheitsbeschränkungen (siehe unten)        |
| `referrerpolicy` | Steuert Referrer-Verhalten                            |
| `allow`       | Spezifiziert Berechtigungen (z. B. `camera`, `fullscreen`)|

---

## 🎯 Beispiel: YouTube-Video

```html
<iframe 
  width="560" 
  height="315" 
  src="https://www.youtube.com/embed/dQw4w9WgXcQ" 
  title="YouTube Video"
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
  allowfullscreen>
</iframe>
```

👉 YouTube bietet angepassten `<iframe>`-Code direkt zum Einbetten.

---

## 🔐 Sandbox & Sicherheit

Das `sandbox`-Attribut beschränkt das Verhalten des eingebetteten Inhalts und verhindert z. B.:

- Formularübermittlungen
- Pop-ups
- Ausführung von Skripten

Beispiel:

```html
<iframe 
  src="https://fremde-seite.de"
  sandbox="allow-same-origin allow-scripts"
  width="800" height="400"
  title="Eingeschränkte Einbettung">
</iframe>
```

| Sandbox-Modifikator        | Beschreibung                                |
|----------------------------|---------------------------------------------|
| `allow-scripts`            | Erlaubt JS (ohne `allow-same-origin` in isolierter Umgebung) |
| `allow-forms`              | Erlaubt Formulare                           |
| `allow-same-origin`        | Ermöglicht Zugriff auf Cookies/Storage      |
| `allow-popups`             | Erlaubt das Öffnen von neuen Tabs           |

---

## ♿ Barrierefreiheit

- Verwende **immer ein `title`-Attribut**, das den Inhalt beschreibt
- Fallback-Inhalt im `<iframe>` ist optional, aber hilfreich
- Nutze `aria-hidden="true"` nur, wenn der eingebettete Inhalt **dekorativ** ist

---

## 🎨 Styling mit CSS

```css
iframe {
  max-width: 100%;
  border: none;
  border-radius: 10px;
  aspect-ratio: 16 / 9;
}
```

---

## ❌ Häufige Fehler

| Fehler                                | Besser                                            |
|---------------------------------------|---------------------------------------------------|
| Kein `title`-Attribut                 | Immer für Screenreader setzen                    |
| Volle Breite ohne Responsivität       | CSS mit `max-width`, `aspect-ratio` nutzen       |
| `iframe` ohne `sandbox` bei Fremdinhalten | Immer absichern bei unbekannten Quellen        |

---

## 🔄 Alternativen und Vergleich

| Zweck                  | Besser geeignetes Element    |
|------------------------|------------------------------|
| Bildanzeige            | `<img>`                      |
| Interaktive Videos     | `<video>` (lokal) / `<iframe>` (extern) |
| Layout-Container       | `<div>`                      |
| Dokumentenvorschau     | `<embed>` oder `<object>`    |

---

## 📚 Fazit

`<iframe>` ist ein mächtiges HTML-Werkzeug, um **fremde Inhalte sicher und flexibel einzubetten**.  
Mit `sandbox`, `loading="lazy"` und responsivem CSS kannst du Performance, Sicherheit und UX optimieren.
