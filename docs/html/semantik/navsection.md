# 🔍 `<nav>` vs. `<section>` – Unterschiede und Anwendung

## 🧩 Gemeinsamkeiten

Sowohl `<nav>` als auch `<section>` sind **semantische HTML5-Elemente**, die dazu dienen, Inhalte **logisch zu strukturieren** und deren **Bedeutung** für Browser, Suchmaschinen und Screenreader zu klären.

Aber: **Sie erfüllen ganz unterschiedliche Zwecke** – die Wahl zwischen beiden hängt davon ab, **was für eine Art von Inhalt du darstellst**.

---

## 🗺️ `<nav>` – Navigationselement

### ✅ Zweck

Das `<nav>`-Element dient dazu, **Navigationsblöcke** zu kennzeichnen. Es beinhaltet **Links zu anderen Bereichen der Website** oder zu wichtigen externen Seiten.

> 🔑 **Inhalt des `<nav>` ist ein Verzeichnis, nicht ein Kapitel.**

### 💡 Typische Inhalte

- Hauptnavigation (Menü)
- Fußzeilen-Navigation
- Breadcrumbs
- Inhaltsverzeichnis
- Paginierung (z. B. „Zurück / Weiter“)

### 🧪 Beispiel

```html
<nav>
  <ul>
    <li><a href="/home">Startseite</a></li>
    <li><a href="/produkte">Produkte</a></li>
    <li><a href="/kontakt">Kontakt</a></li>
  </ul>
</nav>
```

👉 Der Browser, Screenreader oder eine Suchmaschine versteht: **Das sind wichtige Links zur Orientierung**.

---

## 📑 `<section>` – Themenblock

### ✅ Zweck

Ein `<section>` ist ein **inhaltlich abgeschlossener Bereich**, der einen **Teil des Dokuments** behandelt.  
Es wird verwendet, um Inhalte **thematisch zu gliedern**, z. B. Kapitel, Artikelabschnitte, Themenbereiche.

> 🧠 **Ein `<section>` ist ein Kapitel. Ein `<nav>` ist ein Inhaltsverzeichnis.**

### 💡 Typische Inhalte

- Startseitenteaser: „Unsere Leistungen“, „Über uns“
- Artikelabschnitte
- Widgetbereiche auf einer Landingpage
- Informationsblöcke mit Überschrift

### 🧪 Beispiel

```html
<section>
  <h2>Unsere Dienstleistungen</h2>
  <p>Wir bieten individuelle Beratung, Webentwicklung und SEO-Optimierung.</p>
</section>
```

👉 Screenreader erkennt: Dies ist ein **inhaltlicher Abschnitt mit eigener Überschrift**.

---

## 🧠 Wichtige Unterschiede

| Merkmal           | `<nav>`                                | `<section>`                          |
|-------------------|-----------------------------------------|--------------------------------------|
| Funktion          | Navigationsbereich                     | Thematischer Inhaltsbereich          |
| Typischer Inhalt  | Links zu anderen Seiten/Abschnitten    | Text, Medien, Komponenten, Überschrift |
| Screenreader      | Wird als Navigationsmenü angekündigt   | Wird als Abschnitt mit Titel gelesen |
| Anzahl pro Seite  | Mehrfach erlaubt, aber sparsam nutzen  | Beliebig viele möglich               |
| SEO-Auswirkung    | Verstärkt Linkstruktur der Seite       | Erhöht strukturelle Klarheit für Content |

---

## 🔄 Wann was?

| Situation                                           | Verwende |
|-----------------------------------------------------|----------|
| Du baust ein Hauptmenü, Breadcrumbs oder Paginierung | `<nav>` |
| Du strukturierst eine Landingpage in Bereiche       | `<section>` |
| Du listest verwandte Artikel, Links oder Themen     | `<section>` (außer es ist primär Navigation → `<nav>`) |
| Du möchtest Screenreader sagen: „Das ist Navigation“ | `<nav>` |

---

## ❌ Häufige Fehler

| Fehler                                           | Besser mit |
|--------------------------------------------------|------------|
| `<nav>` für Inhaltsabschnitte ohne Links         | `<section>` |
| `<section>` ohne Überschrift                     | `<div>` oder strukturierte Ergänzung |
| Zu viele `<nav>`-Elemente auf einer Seite        | Nur für **bedeutende Navigationen** nutzen |
| `<nav>` enthält nur Social Icons ohne Zweck      | Wahrscheinlich `<footer>` oder `<ul>` besser geeignet |

---

## 📚 Fazit

| Element | Wann verwenden? |
|---------|-----------------|
| ✅ **`<nav>`** | Wenn du **Navigationsbereiche** mit Links zu wichtigen Seiten anbietest |
| ✅ **`<section>`** | Wenn du **thematische Inhaltsblöcke** strukturierst, die **eine eigene Überschrift** haben |

Beide Elemente tragen dazu bei, deine Seite **semantisch korrekt**, **zugänglich** und **maschinenlesbar** zu machen.
