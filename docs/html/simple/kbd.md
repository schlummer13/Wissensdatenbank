# `<kbd>` – Tastatureingabe anzeigen

## 🧩 Funktion

Das `<kbd>`-Element (Keyboard Input) wird verwendet, um **Tasteneingaben oder Tastenkombinationen** darzustellen.  
Typischerweise wird der Text in **Monospace-Schrift** angezeigt – oft stilisiert wie eine Taste.

> 📌 Ideal für Anleitungen, Tutorials, Shortcuts oder Formulare mit Tastatureingabe.

---

## ✅ Verwendung

```html
<p>Drücke <kbd>Strg</kbd> + <kbd>S</kbd>, um zu speichern.</p>
```

👉 So entsteht ein klar erkennbares Tastenkürzel.

---

## 🔧 Attribute

| Attribut | Beschreibung                    |
|----------|---------------------------------|
| `class`  | Für Styling z. B. als Taste     |
| `id`     | Für Interaktionen mit JS       |
| `title`  | Tooltip zur Zusatzinfo         |

---

## 🎨 Beispiel mit CSS

```css
kbd {
  background: #eee;
  border: 1px solid #ccc;
  padding: 2px 5px;
  border-radius: 3px;
  font-family: monospace;
}
```

---

## 🧠 Typische Einsatzbereiche

- Keyboard-Shortcuts
- Text-Editor-Befehle
- Formulareingaben
- Barrierearme Navigationserklärungen

---

## ❌ Fehler vermeiden

| Fehler | Besser |
|--------|--------|
| Nur `<code>` für Tastenkürzel | Verwende `<kbd>` für Eingaben |
| Lange Texte im `<kbd>`        | Nur für **konkrete Tasten** gedacht |

---

## 📚 Fazit

Nutze `<kbd>`, wenn du dem Nutzer **explizit Tasten oder Kombinationen** zeigen willst – ideal für UX und Dokumentation.