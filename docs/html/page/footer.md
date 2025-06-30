# `<footer>` – Seiten- oder Abschnittsfuß

## 🧩 Funktion

Das `<footer>`-Element kennzeichnet den **abschließenden Bereich eines Dokuments oder Abschnitts**.  
Ein Footer kann für die gesamte Webseite gelten oder für ein einzelnes `<article>`, `<section>` oder `<main>`-Element.  
Typischer Inhalt sind:

- Impressum, Datenschutz, Copyright
- Kontaktinformationen
- Navigationslinks (z. B. Sitemap, Hilfe)
- Autoreninfos
- Social-Media-Icons
- letzte Aktualisierung

> 📌 `<footer>` ist ein **semantisch bedeutungsvolles Element**, das den **Kontextabschluss** signalisiert.

---

## ✅ Verwendung

### 1. Seitenweiter Footer

```html
<footer>
  <p>&copy; 2025 Meine Website</p>
  <nav>
    <a href="/impressum">Impressum</a> |
    <a href="/kontakt">Kontakt</a>
  </nav>
</footer>
```

### 2. Footer innerhalb eines Artikels

```html
<article>
  <h2>Blogartikel</h2>
  <p>Inhalt des Artikels...</p>
  <footer>
    <p>Verfasst von Florian Fenzl am <time datetime="2025-06-08">8. Juni 2025</time></p>
  </footer>
</article>
```

---

## 🔧 Attribute

| Attribut   | Beschreibung                                                   |
|------------|----------------------------------------------------------------|
| `id`       | Für Verlinkungen oder JavaScript-Referenzen                   |
| `class`    | Für individuelles Styling                                      |
| `role`     | ARIA-Rolle wie `contentinfo` (empfohlen für Barrierefreiheit) |
| `data-*`   | Eigene JS-Datenattribute                                       |
| `style`    | Inline-CSS (optional)                                          |

---

## 🎨 Beispiel mit CSS

```css
footer {
  background-color: #f2f2f2;
  padding: 2rem;
  font-size: 0.9rem;
  color: #444;
  text-align: center;
}
```

---

## 🧠 Strukturhinweise

- Pro **Seite nur ein Haupt-`<footer>`** im `<body>`-Kontext verwenden
- Innerhalb von `<article>`, `<section>`, `<main>` erlaubt, wenn dort **Abschlussinfos** enthalten sind
- Kein Muss für jede Seite – aber **sehr empfohlen**

---

## ♿ Barrierefreiheit

- Durch `role="contentinfo"` können Screenreader den Bereich als **Meta-Info oder Abschluss** erkennen
- Unterstützt die Navigierbarkeit für Tastatur- oder Screenreader-Nutzer:innen

---

## ❌ Häufige Fehler

| Fehler                                      | Besser                                                  |
|---------------------------------------------|----------------------------------------------------------|
| Footer nur mit `<div>` umgesetzt             | `<footer>` bietet semantischen Mehrwert                |
| Inhaltlich unpassende Infos (z. B. Navigation ohne Bezug) | Footer sollte **abschlussrelevante Inhalte** enthalten |
| Mehrere Haupt-Footer auf einer Seite         | Nur **einen Footer auf oberster Ebene** verwenden       |

---

## 📚 Fazit

Das `<footer>`-Element ist ideal für **abschließende Informationen**, egal ob für die ganze Seite oder einzelne Inhaltsblöcke.  
Es verbessert die **semantische Struktur**, **Barrierefreiheit** und **Lesbarkeit** moderner Webseiten – und gehört zu den wichtigsten Elementen für eine saubere HTML-Grundstruktur.

