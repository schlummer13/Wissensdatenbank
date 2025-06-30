# 🧱 Grundstruktur eines HTML-Dokuments

Ein HTML-Dokument folgt einer festen Grundstruktur. Diese Struktur hilft dem Browser, die Inhalte korrekt darzustellen und zu interpretieren.

---

## 📄 Beispiel: Grundgerüst

```html
<!DOCTYPE html>
<html lang="de">
  <head>
    <meta charset="UTF-8" />
    <title>Meine Webseite</title>
  </head>
  <body>
    <h1>Willkommen!</h1>
    <p>Dies ist meine erste HTML-Seite.</p>
  </body>
</html>
```

---

## 🔍 Erklärung der Bestandteile

| Element                | Beschreibung |
|------------------------|--------------|
| `<!DOCTYPE html>`      | Gibt an, dass es sich um ein HTML5-Dokument handelt. Wichtig für die Browserdarstellung. |
| `<html lang="de">`     | Wurzel-Tag des Dokuments. Das Attribut `lang="de"` gibt die Sprache (Deutsch) an. |
| `<head>`               | Enthält **Meta-Informationen**, die nicht direkt sichtbar sind, z. B. Titel, Zeichencodierung, Stylesheets, Skripte. |
| `<meta charset="UTF-8">` | Gibt die Zeichenkodierung an. UTF-8 ist Standard und unterstützt alle Zeichen. |
| `<title>`              | Der Titel der Seite – wird im Tab des Browsers angezeigt. |
| `<body>`               | Der sichtbare Inhalt der Webseite (Text, Bilder, Links etc.) |
| `<h1>`, `<p>` usw.     | Strukturierende Tags für Überschriften, Absätze usw. – sie erscheinen direkt im Browserfenster. |

---

## ✅ Zusätzliche Hinweise

- **Nur ein `<html>`-, `<head>`- und `<body>`-Tag pro Dokument** erlaubt.
- Der `<head>` enthält keine sichtbaren Inhalte – dafür ist ausschließlich der `<body>` da.
- Die Einhaltung dieser Struktur verbessert **Kompatibilität, Barrierefreiheit und SEO**.

---

## 💡 Tipps

- Immer `<!DOCTYPE html>` verwenden, damit der Browser im sogenannten **Standards-Modus** rendert.
- Achte auf saubere Einrückung – das erhöht die Lesbarkeit.
- Nutze `lang="..."` für Sprachdefinition – wichtig für Suchmaschinen und Screenreader.
