# `<time>` – Zeit- und Datumsangabe

## 🧩 Funktion

Das `<time>`-Element wird verwendet, um **Zeitpunkte oder Zeiträume** anzugeben – sowohl für **Menschen sichtbar** als auch für **Maschinen interpretierbar** (z. B. Suchmaschinen, Kalender, Browser, Screenreader).  
Mit dem `datetime`-Attribut wird eine **standardisierte Zeitangabe** mitgeliefert, die von Maschinen verarbeitet werden kann – z. B. für Reminder, strukturierte Daten, Kalenderfunktionen, RSS-Feeds u. v. m.

> 📌 `<time>` bringt semantische Bedeutung für Zeitinformationen und ermöglicht eine **strukturierte Verarbeitung von Datum/Zeit** durch Suchmaschinen & Tools.

---

## ✅ Verwendung

```html
<p>Der Artikel wurde am <time datetime="2025-06-08">8. Juni 2025</time> veröffentlicht.</p>
```

👉 Der Leser sieht ein schönes, formatiertes Datum – Maschinen erkennen exakt: **2025-06-08**.

---

## 🔧 Attribute

| Attribut   | Beschreibung |
|------------|--------------|
| `datetime` | Pflicht für maschinenlesbare Zeitformate (ISO 8601) |
| `class`    | Für visuelles Styling über CSS |
| `id`       | Für Verlinkung oder JavaScript-Zugriff |
| `title`    | Tooltip mit ergänzenden Infos |

---

## 🎯 Anwendungsbeispiele

### 1. 📅 Datum eines Events

```html
<p>Unser Webinar findet am <time datetime="2025-07-01">1. Juli 2025</time> statt.</p>
```

### 2. ⏳ Zeitspanne (mit Start–Ende)

```html
<p>Das Projekt lief von 
  <time datetime="2024-01-01">Januar 2024</time> 
  bis 
  <time datetime="2024-12-31">Dezember 2024</time>.
</p>
```

### 3. ⏰ Uhrzeit

```html
<p>Der Livestream startet um <time datetime="14:00">14:00 Uhr</time>.</p>
```

### 4. 📆 Kombination mit Kalender-Apps

Suchmaschinen und Kalenderanwendungen können `<time>`-Elemente auslesen und z. B. **als strukturierte Daten (Schema.org)** verarbeiten.

---

## 🧠 ISO 8601 – gültige `datetime`-Formate

| Formattyp        | Beispiel               | Bedeutung                    |
|------------------|------------------------|------------------------------|
| Datum            | `2025-06-08`           | 8. Juni 2025                 |
| Uhrzeit          | `14:30`                | 14:30 Uhr                    |
| Datum + Uhrzeit  | `2025-06-08T14:30`     | 8. Juni 2025, 14:30 Uhr      |
| Mit Zeitzone     | `2025-06-08T14:30+02:00` | 8. Juni 2025, MESZ          |
| Wochentag (nicht zulässig in `datetime`) | `Monday` | (visuell ja, maschinell nein) |

---

## ♿ Barrierefreiheit & Semantik

- Screenreader erkennen `<time>` als Zeitinformation und können sie entsprechend **vorlesen oder betonen**
- Strukturierte Daten helfen Assistenzsystemen, Datums-/Zeitangaben korrekt einzuordnen
- Barrierefreie Tooltip-Texte können zusätzlich über `title` ergänzt werden

---

## ❌ Häufige Fehler

| Fehler                                       | Besser                                        |
|----------------------------------------------|-----------------------------------------------|
| Nur visueller Text ohne `datetime`-Attribut  | `<time datetime="...">...</time>` verwenden   |
| Falsches Datumsformat im `datetime`          | Immer ISO 8601 (z. B. `YYYY-MM-DD`) nutzen    |
| Zeiträume in einem einzigen `<time>`-Element | Besser: Zwei `<time>`-Elemente (Start und Ende) |
| `<time>` nur fürs Styling                    | Verwende nur, wenn wirklich Zeitinformation   |

---

## 📚 Fazit

Das `<time>`-Element ist ein **modernes, semantisch korrektes Werkzeug**, um **Datums- und Zeitangaben maschinenlesbar** in HTML zu integrieren. Es verbessert die **Struktur, Auffindbarkeit und Nutzbarkeit** von Zeitdaten für Benutzer und Systeme – von Suchmaschinen bis hin zu Kalender-Plugins und Screenreadern.
