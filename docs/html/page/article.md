# `<article>` – Eigenständiger Inhaltsblock

## 🧩 Funktion

Das `<article>`-Element steht für **einen eigenständigen, in sich geschlossenen Inhaltsabschnitt**, der auch **außerhalb des Kontexts** der aktuellen Seite verständlich ist.  
Typische Beispiele sind:

- Blogbeiträge
- Nachrichtenartikel
- Forenbeiträge
- Nutzerkommentare
- Einträge in einem RSS-Feed
- Produktbeschreibungen

> 📌 Inhalte in `<article>` sollen **für sich alleine stehen können**, z. B. in Feeds, Suchergebnissen oder Druckausgaben.

---

## ✅ Verwendung

```html
<article>
  <h2>Neues Feature im Produkt</h2>
  <p>Wir haben ein neues Tool integriert, das automatisch Daten analysiert.</p>
</article>
```

👉 Der `<h2>` gehört zum Artikel – jeder Artikel kann (und sollte) eine eigene Überschrift haben.

---

## 🧠 Semantische Bedeutung

- Der Inhalt ist **thematisch eigenständig**
- Kann in anderen Kontexten **weiterverwendet** werden (z. B. als Einzelseite oder in einem Aggregator)
- Ist **nicht nur eine Gruppierung**, sondern hat redaktionellen oder strukturellen Eigenwert

---

## 🔧 Häufig verwendete Elemente im `<article>`

| Element         | Funktion                                        |
|------------------|-------------------------------------------------|
| `<header>`       | Titel, Autor, Datum, ggf. Bild                  |
| `<footer>`       | Quelle, Kommentare, Tags, Weiterlesen-Link      |
| `<h1>`–`<h6>`     | Artikelüberschrift (meist `<h2>` in der Seite) |
| `<section>`      | Inhaltlich untergeordnete Bereiche              |
| `<p>`, `<img>`, `<figure>` | Fließtext, Bilder etc.             |

---

## 🧪 Erweiterte Beispiele

### Blogeintrag mit Datum & Autor

```html
<article>
  <header>
    <h2>Wie funktioniert HTML?</h2>
    <p><time datetime="2025-06-08">8. Juni 2025</time> von <span class="author">Florian Fenzl</span></p>
  </header>

  <p>HTML ist die Grundlage des Webs...</p>

  <footer>
    <a href="/kommentare.html">5 Kommentare</a>
  </footer>
</article>
```

---

## 🎯 Unterschiede zu anderen Tags

| Element      | Zweck                                  |
|--------------|-----------------------------------------|
| `<div>`      | Rein visuelle Gruppierung (ohne Bedeutung) |
| `<section>`  | Thematischer Bereich (z. B. Kapitel)       |
| `<article>`  | Eigenständiger, kontextunabhängiger Inhalt |

> ✅ Verwende `<section>` **innerhalb von `<article>`**, nicht umgekehrt!

---

## ♿ Barrierefreiheit & Struktur

- Screenreader erkennen `<article>` als **eigenen Bereich**
- Nutzer können zwischen Artikeln **navigieren**
- Auch für strukturierte Daten (Schema.org `Article`) gut geeignet

---

## ❌ Fehler vermeiden

| Fehler                                    | Besser                                     |
|-------------------------------------------|---------------------------------------------|
| `<article>` ohne Überschrift              | Immer mit `<h2>` oder vergleichbarem Titel |
| Einsatz für bloße Layout-Gruppierung      | Dafür `<div>` oder `<section>` verwenden  |
| Artikel mit irrelevanten Inhalten füllen  | Inhalt sollte eigenständig sinnvoll sein   |

---

## 📚 Fazit

Das `<article>`-Element ist ideal für **wiederverwendbare, thematisch abgeschlossene Inhalte** – von Blogposts bis Produktbeschreibungen.  
Es unterstützt die **Strukturierung**, **Barrierefreiheit** und **Maschinenlesbarkeit** deiner Inhalte – eine klare Empfehlung für moderne Webentwicklung.

