# `<var>` – Variable oder Platzhalter

## 🧩 Funktion

Das `<var>`-Element kennzeichnet **Variablen, mathematische Symbole oder Platzhalternamen** in Text oder Code.  
Es hat semantische Bedeutung und wird **meist kursiv** dargestellt.

> 📌 Für mathematische Formeln, Codebeispiele oder allgemeine Platzhalter ideal.

---

## ✅ Verwendung

```html
<p>Die Fläche berechnet sich mit <var>a</var> × <var>b</var>.</p>
```

👉 „a“ und „b“ werden als **Variable** ausgezeichnet – visuell und semantisch.

---

## 🔧 Attribute

| Attribut | Beschreibung               |
|----------|----------------------------|
| `class`  | Für eigenes Styling        |
| `title`  | Optionaler Hinweistext     |
| `id`     | Für gezielte JS-Zugriffe   |

---

## 🎨 Beispiel mit CSS

```css
var {
  font-style: italic;
  color: #005;
}
```

---

## 🧠 Typische Einsatzbereiche

- Variablen in mathematischen Formeln
- Funktionsparameter oder Platzhalter in Code
- Technische Beschreibungen mit Parametern

---

## ❌ Fehler vermeiden

| Fehler                 | Besser                                    |
|------------------------|--------------------------------------------|
| `<var>` für Funktionsnamen | Verwende `<code>` oder `<dfn>`          |
| `<i>` für Variablen     | Nutze `<var>` für semantische Bedeutung  |

---

## 📚 Fazit

Nutze `<var>`, wenn du **technische oder mathematische Variablen** klar auszeichnen willst – in Kombination mit `<code>`, `<samp>` und `<dfn>` besonders effektiv.