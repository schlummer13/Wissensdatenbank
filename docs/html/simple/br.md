# `<br>` – Zeilenumbruch (Break)

## 🧩 Funktion

Das `<br>`-Element steht für „break“ und wird verwendet, um einen **manuellen Zeilenumbruch** innerhalb eines Textblocks zu erzwingen – ohne einen neuen Absatz zu beginnen.  
Es wird vor allem dort eingesetzt, wo ein einfacher Umbruch **stilistisch oder inhaltlich notwendig ist**, ohne dabei die **semantische Bedeutung eines Absatzes** zu verändern.

> 📌 `<br>` erzeugt nur einen visuellen Zeilenumbruch – der Inhalt bleibt Teil desselben Absatzes.

---

## ✅ Verwendung

```html
<p>
  Name: Max Mustermann<br />
  Straße: Musterweg 1<br />
  Ort: 12345 Musterstadt
</p>
```

👉 Alle Angaben erscheinen in separaten Zeilen, aber innerhalb desselben `<p>`-Blocks.

---

## 🔧 Besonderheiten

| Merkmal            | Beschreibung                                 |
|--------------------|----------------------------------------------|
| Selbstschließend   | `<br>` hat **kein öffnendes/schließendes Paar** – es endet in sich selbst |
| Inline-Element     | Es wirkt **innerhalb von Textfluss**         |
| Semantikfrei       | Keine inhaltliche Bedeutung, rein visuell    |
| Keine Attribute    | `<br>` hat **keine typischen Attribute** – in der Regel auch keine `class`, `id` o. Ä. nötig |

---

## 🧪 Anwendungsbeispiele

### 1. 📄 Formatierter Adressblock

```html
<p>
  Max Mustermann<br />
  Beispielstraße 5<br />
  12345 Musterstadt
</p>
```

### 2. 🎵 Liedtext oder Gedicht

```html
<p>
  Der Mond ist aufgegangen,<br />
  die goldnen Sternlein prangen<br />
  am Himmel hell und klar.
</p>
```

### 3. 🧾 Formulareingabe mit Etikett

```html
<label>
  Kommentar:<br />
  <textarea></textarea>
</label>
```

---

## ⚠️ Wann **nicht** `<br>` verwenden?

| Falsch eingesetzt bei...              | Besser stattdessen:     |
|--------------------------------------|--------------------------|
| Gliederung von Absätzen              | `<p>` verwenden          |
| Abständen zwischen Blöcken           | CSS (`margin`, `padding`)|
| Strukturierung von Inhalten          | Semantische Tags (`<ul>`, `<section>`, etc.) |
| Layout von Formularen oder Tabellen  | CSS-Layout (Flexbox, Grid, Table) |

---

## ♿ Barrierefreiheit & Zugänglichkeit

- `<br>` wird von Screenreadern meist als „Pause“ oder **„Umbruch“ ohne semantische Pause** interpretiert
- Für bedeutungsvolle Trennung (z. B. Sinnabschnitte, Listen, Themenblöcke) sollte man stattdessen **strukturierende HTML-Tags** verwenden
- Bei Gedichten oder Liedtexten kann `<br>` jedoch eine **verständliche Darstellung** fördern

---

## ❌ Häufige Fehler

| Fehler                                         | Besser                                       |
|-----------------------------------------------|----------------------------------------------|
| Mehrere `<br><br>` statt `<p>`                | Verwende `<p>` für echte Absätze             |
| Nutzung von `<br>` für vertikale Abstände     | Verwende CSS (`margin`, `padding`)           |
| `<br>` in Layoutblöcken als Positionierung    | CSS-Layoutmodelle (Flexbox, Grid, etc.)      |

---

## 📚 Fazit

Das `<br>`-Tag ist ein **kleines, aber praktisches HTML-Werkzeug** für feine Textformatierungen.  
Es eignet sich gut für **Adresszeilen, Liedtexte, Gedichte oder technische Formulare**, sollte aber **nicht als Layout-Ersatz** oder für semantische Gliederung verwendet werden.

> 💬 Als Nächstes: Möchtest du mit `<hr>`, `<mark>` oder anderen Inline-Textformatierungen weitermachen?