# `<textarea>` – Mehrzeiliges Texteingabefeld

## 🧩 Funktion

Das `<textarea>`-Element wird verwendet, um **mehrzeilige Texteingaben** zu ermöglichen – z. B. für Kommentare, Nachrichten, Feedback oder Artikel. Im Gegensatz zu `<input type="text">` erlaubt es den Benutzer, **ganze Absätze** zu schreiben und selbst Zeilenumbrüche einzufügen.

---

## ✅ Grundstruktur

```html
<textarea name="nachricht"></textarea>
```

**Was passiert?**  
👉 Erstellt ein einfaches mehrzeiliges Texteingabefeld ohne Begrenzung der Größe oder Zeichenanzahl.

---

## 🔧 Wichtige Attribute

| Attribut        | Beschreibung |
|-----------------|--------------|
| `name`          | Schlüsselname für das Formular / Backend |
| `id`            | Eindeutige ID für Verbindung mit `<label>` |
| `rows`          | Höhe (Anzahl der Textzeilen) |
| `cols`          | Breite (Anzahl der Zeichen pro Zeile – veraltet, CSS bevorzugt) |
| `placeholder`   | Platzhaltertext, der bei leerem Feld angezeigt wird |
| `maxlength`     | Maximale Zeichenanzahl |
| `minlength`     | Minimale Zeichenanzahl |
| `required`      | Pflichtfeld |
| `readonly`      | Eingabe ist nicht änderbar |
| `disabled`      | Feld ist deaktiviert |
| `autocomplete`  | Vorschläge vom Browser erlauben (`on` / `off`) |
| `wrap`          | Umbruchverhalten bei Zeilenende (`soft`, `hard`, `off`) |

---

## 🧪 Beispiele

### 1. ✍ Standard-Textarea mit Platzhalter

```html
<label for="kommentar">Kommentar:</label><br />
<textarea id="kommentar" name="kommentar" rows="5" cols="40" placeholder="Deine Meinung ..."></textarea>
```

👉 Bietet dem Benutzer ein Eingabefeld für bis zu 5 Zeilen.

---

### 2. 📏 Begrenzte Zeichenzahl

```html
<form>
  <label for="feedback">Feedback (max. 250 Zeichen):</label><br />
  <textarea id="feedback" name="feedback" rows="6" maxlength="250" required></textarea>
  <br />
  <button type="submit">Absenden</button>
</form>
```

👉 Benutzer kann maximal 250 Zeichen eingeben – ideal für limitierte Eingaben wie Bewertungen.

---

### 3. 🔒 Nur-lesbar

```html
<textarea readonly>Dies ist ein schreibgeschütztes Textfeld.</textarea>
```

👉 Eingabe nicht möglich, aber Inhalt kann kopiert werden.

---

### 4. 🚫 Deaktiviert

```html
<textarea disabled>Dieses Feld ist deaktiviert.</textarea>
```

👉 Feld wird ausgegraut und beim Absenden nicht übertragen.

---

### 5. 🔁 Zeilenumbruch kontrollieren mit `wrap`

```html
<textarea name="beschreibung" wrap="hard" rows="4" cols="50">
Dieser Text wird mit Zeilenumbruch abgespeichert.
</textarea>
```

| Wert      | Verhalten |
|-----------|-----------|
| `soft`    | Text wird **im Formular umbrochen**, aber **ohne** Zeilenumbrüche im gesendeten Wert |
| `hard`    | Text wird **mit echten Zeilenumbrüchen** gespeichert |
| `off`     | Kein automatischer Umbruch, horizontales Scrollen möglich |

---

## 🧠 Tipps für bessere Benutzerfreundlichkeit

- Verwende `<label>`-Elemente für bessere Zugänglichkeit.
- Nutze `rows` nur als **Startgröße**, die tatsächliche Größe kann durch den Benutzer verändert werden (je nach Browser).
- Vermeide `cols`, verwende stattdessen **CSS mit `width`**.
- Begrenze mit `maxlength`, um unnötig lange Texte zu verhindern.
- Binde JavaScript ein, um Zeichen-Zähler anzuzeigen oder Live-Validierung durchzuführen.

---

## 💡 Zeichen-Zähler (einfaches Beispiel mit JS)

```html
<label for="kommentar">Kommentar (max. 200 Zeichen):</label>
<textarea id="kommentar" maxlength="200"></textarea>
<p id="counter">200 Zeichen übrig</p>

<script>
  const textarea = document.getElementById("kommentar");
  const counter = document.getElementById("counter");

  textarea.addEventListener("input", () => {
    const remaining = 200 - textarea.value.length;
    counter.textContent = `${remaining} Zeichen übrig`;
  });
</script>
```

👉 Hilft dem Benutzer, die erlaubte Textlänge einzuhalten.

---

## 📚 Fazit

Das `<textarea>`-Element ist ideal für **freie Texteingaben** mit mehr als einer Zeile. Ob für Kommentare, E-Mails oder Supportanfragen – es gehört zu den wichtigsten Formularelementen. In Kombination mit CSS, Validierung und sinnvoller UX lässt sich daraus ein leistungsfähiges Textelement gestalten.
