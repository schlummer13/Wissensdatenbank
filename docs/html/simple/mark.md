# `<mark>` – Hervorgehobener Text

## 🧩 Funktion

Das `<mark>`-Element wird verwendet, um **Textstellen hervorzuheben**, die für den aktuellen Zusammenhang **besonders relevant oder auffällig** sind.  
Standardmäßig erscheint der Text mit einem **gelben Hintergrund**, ähnlich wie bei einem Textmarker.

> 📌 Semantisch bedeutet `<mark>`, dass der markierte Text eine **temporäre Relevanz** hat – etwa zur Hervorhebung von Suchbegriffen oder aktuellen Kontextbezügen.

---

## ✅ Verwendung

```html
<p>Sie haben nach <mark>Maschinelles Lernen</mark> gesucht.</p>
```

👉 Der markierte Ausdruck fällt visuell ins Auge und signalisiert: **Dieser Text ist in diesem Moment besonders wichtig.**

---

## 🎯 Semantische Bedeutung

| Einsatzgebiet                           | Beispiel                                        |
|----------------------------------------|-------------------------------------------------|
| Suchergebnisse                          | Markierte Treffer im Text                      |
| Kommentierte Änderungen / Redaktionen  | Neu hinzugefügter oder geänderter Text         |
| Fokus auf Begriffen bei Tooltips, Glossaren | Begriffe bei Mouseover oder Kontextbezug    |
| Interaktive Lernumgebungen             | Markierte Lösungen oder Hinweise               |

---

## 🔧 Attribute

| Attribut | Beschreibung |
|----------|--------------|
| `class`  | Für CSS-Styling (z. B. Farbe ändern) |
| `style`  | Direktes Inline-Styling              |
| `id`     | Identifikation für JavaScript        |
| `lang`   | Sprachkennung für Screenreader       |
| `title`  | Hinweistext bei Mouseover            |

---

## 🎨 Beispiel mit CSS

```html
<p>
  Die Variable <mark class="code-hint">x</mark> repräsentiert das Ergebnis.
</p>
```

```css
.code-hint {
  background-color: lightgreen;
  color: black;
  font-weight: bold;
}
```

👉 Mit CSS kannst du `<mark>` an das Design deiner Seite anpassen (z. B. bei dunklen Hintergründen).

---

## ⚖️ Unterschied zu anderen Hervorhebungen

| Element      | Bedeutung                      | Stil        | Verwendung                        |
|--------------|---------------------------------|-------------|-----------------------------------|
| `<mark>`     | Temporär relevant im Kontext    | Gelb        | Suchtreffer, aktuelle Hinweise    |
| `<strong>`   | Wichtigkeit / Dringlichkeit     | Fett        | Warnungen, Anweisungen            |
| `<em>`       | Betonung                        | Kursiv      | Sprachlich betonte Passagen       |
| `<span>`     | Keine Semantik – rein visuell   | beliebig    | Frei für Design & CSS             |

---

## ♿ Barrierefreiheit & Semantik

- Screenreader geben `<mark>`-Inhalte möglicherweise als „hervorgehoben“ aus – je nach Unterstützung
- Für barrierefreie Hervorhebungen sollte `<mark>` mit **zusätzlichem Kontext oder `aria-label`** ergänzt werden, wenn nötig
- Visuell sollte der Kontrast zum Text ausreichend hoch sein → Kontrast mit CSS ggf. anpassen

---

## ❌ Häufige Fehler

| Fehler                                      | Besser                                        |
|---------------------------------------------|-----------------------------------------------|
| `<mark>` als reines Stilmittel              | Nur verwenden, wenn Text **inhaltlich relevant** ist |
| Markierung ohne Aussage oder Kontext        | Lieber `<span>` + CSS nutzen                  |
| Zu viele Markierungen im Fließtext          | Selektiv & gezielt einsetzen                  |
| Geringer Farbkontrast bei Custom-Styling    | Gute Lesbarkeit und Kontrast sicherstellen    |

---

## 📚 Fazit

Das `<mark>`-Element ist ein **semantisch sinnvolles Werkzeug**, um Textpassagen hervorzuheben, die **im aktuellen Kontext besondere Aufmerksamkeit verdienen**.  
Es kombiniert **visuelle Wirkung mit semantischer Aussagekraft** – ideal für Suchanwendungen, Lernplattformen, Leseführung und interaktive Interfaces.
