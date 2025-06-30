# `<header>` – Seiten- oder Abschnittskopf

## 🧩 Funktion

Das `<header>`-Element kennzeichnet den **Einleitungsbereich** eines HTML-Dokuments oder eines Abschnitts wie `<article>`, `<section>`, `<main>` oder `<aside>`.  
Typische Inhalte in einem `<header>` sind:

- **Seitentitel**
- **Logo / Markenname**
- **Navigation**
- **Einführungstexte**
- **Metadaten (z. B. Datum, Autor)**

> 📌 Es handelt sich um ein **semantisches Blockelement**, das Kontext und Einstieg liefert – vergleichbar mit der „Titelseite“ eines Kapitels.

---

## ✅ Verwendung

### 1. Globaler Seitenkopf

```html
<header>
  <h1>Mein Blog</h1>
  <nav>
    <ul>
      <li><a href="/">Start</a></li>
      <li><a href="/artikel">Artikel</a></li>
      <li><a href="/kontakt">Kontakt</a></li>
    </ul>
  </nav>
</header>
```

### 2. Header innerhalb eines Artikels

```html
<article>
  <header>
    <h2>Was ist Data Science?</h2>
    <p>von Florian Fenzl – <time datetime="2025-06-08">8. Juni 2025</time></p>
  </header>
  <p>Data Science ist ein interdisziplinäres Feld ...</p>
</article>
```

---

## 🔧 Attribute

| Attribut | Beschreibung                                               |
|----------|------------------------------------------------------------|
| `id`     | Einzigartiger Bezeichner (z. B. für Links oder JS)         |
| `class`  | CSS-Styling über Klassen                                   |
| `style`  | Direktes Inline-Styling (z. B. Hintergrundfarbe)           |
| `role`   | ARIA-Rolle wie `banner` (nur für das **erste Seitenheader**) |
| `data-*` | Eigene Datenattribute für JS                               |

---

## 🎯 Hinweise zur Nutzung

| Bereich                    | Empfohlenes Verhalten                                |
|----------------------------|------------------------------------------------------|
| Dokument (ganze Seite)     | Nur **ein** `<header>` mit `role="banner"`          |
| Untergeordnete Inhalte     | Jeweils eigener `<header>` für Artikel, Sektionen   |
| Navigation im Header       | Direkt mit `<nav>` kombinieren (optional)           |

---

## 🎨 Beispiel mit CSS

```css
header {
  background-color: #f8f8f8;
  padding: 2rem;
  border-bottom: 1px solid #ddd;
}
```

---

## ♿ Barrierefreiheit (ARIA & Struktur)

- Hauptseitenkopf sollte `role="banner"` erhalten
- Nicht mehrfach auf oberster Ebene mit `role="banner"` markieren
- Headerelemente verbessern die **semantische Navigierbarkeit** für Screenreader

---

## ❌ Häufige Fehler

| Fehler                                      | Korrekte Verwendung                          |
|---------------------------------------------|----------------------------------------------|
| Mehrere `<header>`-Elemente mit `role="banner"` | Nur **einen** pro Seite                      |
| `<header>` für Inhalt statt Einleitung       | Nutze `<section>`, `<div>` oder `<main>`     |
| Nur als Wrapper für Styling genutzt          | Nur verwenden, wenn ein **einleitender Kontext** gemeint ist |

---

## 🔄 Unterschied zu ähnlichen Elementen

| Element   | Zweck                                         |
|-----------|-----------------------------------------------|
| `<header>` | Einstieg/Kopf eines Abschnitts               |
| `<footer>` | Abschluss/Meta eines Abschnitts              |
| `<nav>`    | Navigationselemente                          |
| `<main>`   | Hauptinhalt der Seite                        |

---

## 📚 Fazit

Das `<header>`-Element ist ein **semantisch aussagekräftiger Einstiegspunkt**, der für Seiten und Inhaltsbereiche gleichsam geeignet ist.  
Ob Logo, Navigation oder Titel: Der Header strukturiert Inhalte sinnvoll und verbessert die **Lesbarkeit, SEO und Barrierefreiheit** deiner HTML-Seite.
