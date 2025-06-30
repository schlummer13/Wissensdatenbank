# `<h1>` bis `<h6>` – HTML-Überschriften

## 🧩 Funktion

HTML-Überschriften `<h1>` bis `<h6>` sind **strukturierende Elemente**, die Inhalte **hierarchisch gliedern**.  
Sie geben einem Dokument **semantische Struktur**, erleichtern die **Lesbarkeit**, verbessern die **Barrierefreiheit** und sind **entscheidend für SEO (Suchmaschinenoptimierung)**.

> 📌 Eine gut strukturierte Seite nutzt Überschriften wie ein Inhaltsverzeichnis – von der Hauptüberschrift bis zu feinen Unterpunkten.

---

## 🔢 Hierarchie & Bedeutung

| Tag     | Ebene         | Typischer Einsatz                        |
|---------|---------------|------------------------------------------|
| `<h1>`  | Haupttitel     | Seitentitel / Dokumentüberschrift       |
| `<h2>`  | 1. Unterebene | Große Inhaltsblöcke / Hauptabschnitte   |
| `<h3>`  | 2. Unterebene | Untergliederung innerhalb eines Themas  |
| `<h4>`  | 3. Unterebene | Feinere Absätze, Unterpunkte            |
| `<h5>`  | 4. Unterebene | Selten genutzt, bei komplexen Layouts   |
| `<h6>`  | 5. Unterebene | Sehr kleine Gliederungseinheiten        |

➡ Überschriften sollen **logisch und chronologisch gestaffelt** werden – **nicht springen** (z. B. von `<h2>` direkt zu `<h5>` vermeiden).

---

## ✅ Syntax & Verwendung

```html
<h1>Was ist HTML?</h1>
  <h2>Einführung</h2>
    <h3>Was bedeutet Markup?</h3>
    <h3>Wofür wird HTML verwendet?</h3>
  <h2>HTML-Grundstruktur</h2>
    <h3>Das head-Element</h3>
    <h3>Das body-Element</h3>
```

### Wichtig:

- Die **`<h1>` sollte nur einmal pro Seite** verwendet werden – sie beschreibt den **zentralen Inhalt**.
- Verwende Überschriften **immer mit inhaltlicher Bedeutung** – **nicht nur zum Stylen** (dafür CSS nutzen).
- Der **sichtbare Text in Überschriften** ist **relevant für SEO** – wähle prägnante, keyword-relevante Formulierungen.

---

## 🎯 Semantik & SEO

- Google und andere Suchmaschinen analysieren die **Struktur anhand der Überschriften-Hierarchie**.
- Eine Seite mit klarer Gliederung wird **besser verstanden und indexiert**.
- Screenreader nutzen Überschriften zur **Navigation** für sehbehinderte Menschen.
- Auch Suchergebnisse und Inhaltsvorschauen (z. B. Featured Snippets) profitieren von klaren `<h1>`- und `<h2>`-Strukturen.

---

## 🔧 Mögliche Attribute

| Attribut | Beschreibung |
|----------|--------------|
| `id`     | Ermöglicht direkte Verlinkung zu einer Überschrift (z. B. Sprunganker mit `#`) |
| `class`  | Zuweisung einer CSS-Klasse für individuelles Styling |
| `style`  | Inline-Styling (nicht empfohlen bei größeren Projekten) |
| `title`  | Zusätzlicher Tooltip-Text beim Überfahren der Überschrift |
| `tabindex` | Ermöglicht Tastaturfokus auf Überschrift (optional bei interaktiven Elementen) |

---

## 🖌️ Beispiel mit CSS-Klasse

```html
<h2 class="kapitel">Einleitung</h2>
```

```css
.kapitel {
  color: #3366cc;
  font-size: 1.6rem;
  margin-bottom: 0.8em;
}
```

---

## ❌ Häufige Fehler

| Fehler                                  | Besser                                      |
|-----------------------------------------|---------------------------------------------|
| Mehrere `<h1>` pro Seite                | Nur ein `<h1>`, danach `<h2>`, `<h3>`, ... |
| `<h3>` ohne vorheriges `<h2>`           | Überschriften hierarchisch aufbauen         |
| Verwendung von `<h1>` nur wegen Schriftgröße | Stil per CSS definieren, nicht per Bedeutung |
| Keine Überschriften auf der Seite       | Struktur fehlt → schlecht für SEO & UX     |

---

## ♿ Barrierefreiheit

- Screenreader-Nutzer können per Tastatur von **Überschrift zu Überschrift springen**
- Eine **logische Überschriftenstruktur** ist ein Muss für **barrierefreie Seiten**
- `<h1>` sollte das **erste Element im sichtbaren Inhalt** sein (nach `<header>` oder `<nav>`)

---

## 📚 Fazit

HTML-Überschriften sind **mehr als nur große Texte** – sie gliedern Inhalte, geben Struktur, helfen bei Navigation und verbessern die Auffindbarkeit deiner Seiten im Web.  
Verwende sie **sorgfältig, durchdacht und hierarchisch** – sowohl für Leser als auch für Maschinen.
