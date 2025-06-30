# `<hr>` – Horizontale Trennlinie (Horizontal Rule)

## 🧩 Funktion

Das `<hr>`-Element steht für „Horizontal Rule“ und wird verwendet, um eine **visuelle und semantische Trennung** zwischen zwei Themen oder Abschnitten innerhalb eines Dokuments darzustellen.  
In modernen HTML5-Seiten trägt `<hr>` zusätzlich **semantische Bedeutung**: Es signalisiert einen **thematischen Bruch** oder eine **inhaltliche Zäsur** im Fließtext.

> 📌 `<hr>` trennt Inhalte nicht nur optisch, sondern auch **logisch** – ähnlich wie ein Kapitelumbruch im Buch.

---

## ✅ Verwendung

```html
<p>Ein Thema</p>
<hr />
<p>Neues Thema</p>
```

👉 Der horizontale Strich zeigt an, dass der folgende Textabschnitt **inhaltlich unabhängig** oder **thematisch abgesetzt** ist.

---

## 🔧 Eigenschaften

| Merkmal         | Beschreibung |
|------------------|--------------|
| Selbstschließend | `<hr>` hat **kein schließendes Tag** – es ist ein leeres Element |
| Block-Level      | Es nimmt standardmäßig die **volle Breite** seines Containers ein |
| Visuell          | Wird vom Browser meist als **graue Linie** dargestellt (per CSS anpassbar) |
| Semantik         | Seit HTML5: **thematische Trennung** eines Dokuments, z. B. zwischen Hauptinhalt und Fußzeile |

---

## 🎨 Beispiel mit CSS-Styling

```html
<hr class="trennung" />
```

```css
.trennung {
  border: none;
  height: 2px;
  background-color: #333;
  margin: 2em 0;
}
```

👉 So kann `<hr>` optisch an das Design angepasst werden (Dicke, Farbe, Abstand etc.).

---

## 📐 Typische Einsatzbereiche

| Einsatz                          | Zweck |
|----------------------------------|-------|
| Zwischen Absätzen                | Thematische Trennung |
| Vor einem Footer oder Fazit      | Abgrenzung vom Hauptinhalt |
| In Blogartikeln oder Newsseiten  | Abschnittswechsel kennzeichnen |
| Innerhalb von Formularen         | Inhaltliche Gruppierung (besser mit `<fieldset>`) |

---

## ♿ Barrierefreiheit & Semantik

- Screenreader interpretieren `<hr>` als **thematische Trennlinie** – z. B. „Trennung“ oder „Horizontale Linie“
- Das kann helfen, Inhalte **besser einzuordnen** und Struktur erkennbar zu machen
- In längeren Texten oder One-Pager-Seiten ist es hilfreich, damit der Nutzer die **gedankliche Gliederung** nachvollziehen kann

---

## ❌ Häufige Fehler

| Fehler                                         | Besser                                       |
|-----------------------------------------------|----------------------------------------------|
| Verwendung als Design-Ersatz (Layout)         | Nutze CSS mit `<div>` oder `border`          |
| Mehrere `<hr>` ohne inhaltliche Funktion      | Nur einsetzen, wenn es eine **Trennfunktion** erfüllt |
| Styling mit Inline-CSS überall                | Lieber per Klasse und externem Stylesheet    |

---

## 📚 Fazit

Das `<hr>`-Tag ist ein **visuelles und semantisches Werkzeug** zur Strukturierung von Inhalten.  
Es signalisiert nicht nur einen **Abschnittswechsel**, sondern verbessert auch die **Lesbarkeit** und **barrierefreie Struktur** von Webseiten – vorausgesetzt, es wird sinnvoll und nicht rein dekorativ eingesetzt.
