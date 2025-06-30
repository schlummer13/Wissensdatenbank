# 🌳 DOM – Nodes

## 🧩 Was ist ein Node?

Im DOM ist **alles ein Node** (dt. „Knoten“).  
Ein HTML-Dokument wird als **Baumstruktur** gespeichert – jede Überschrift, jedes Attribut, jedes Kommentar ist ein Node.

> Man unterscheidet verschiedene Node-Typen.

---

## 🔢 Die wichtigsten Node-Typen

| Typ                    | Beschreibung                         | Beispiel                    |
|-------------------------|--------------------------------------|-----------------------------|
| `Element` (1)           | HTML-Element                         | `<div>`, `<p>`, `<img>`     |
| `Text` (3)              | Reiner Text                          | `"Hallo Welt"`              |
| `Comment` (8)           | Kommentar                            | `<!-- Kommentar -->`        |
| `Document` (9)          | Ganzes Dokument                      | `document`                  |
| `DocumentFragment` (11) | Virtueller Mini-DOM für Vorlagen     | Für schnelle DOM-Bauten     |

---

## 🧪 So prüfst du den Node-Typ

```js
const p = document.querySelector("p");

console.log(p.nodeType); // 1 (Element)
console.log(p.nodeName); // "P"
```

---

## 📦 Zugriff auf Node-Inhalte

```js
const node = document.querySelector("p");

console.log(node.nodeValue); // null (weil es ein Element ist)
console.log(node.textContent); // liefert Textinhalt
console.log(node.innerHTML); // gibt HTML-Inhalt zurück
```

---

## 📚 `nodeType` Werte im Überblick

| Wert | Typ                     |
|------|--------------------------|
| `1`  | Element Node             |
| `3`  | Text Node                |
| `8`  | Comment Node             |
| `9`  | Document Node            |
| `11` | DocumentFragment Node    |

---

## 🧱 Node-Struktur

```html
<p>Hallo <strong>Welt</strong></p>
```

Hat 3 Nodes:

1. `<p>` → Element Node  
2. `"Hallo "` → Text Node  
3. `<strong>Welt</strong>` → Element Node mit eigenem Text Node

---

## 🔄 Kindknoten mit `childNodes`

```js
const p = document.querySelector("p");

console.log(p.childNodes); // gibt alle Knoten zurück (auch Text!)
```

📌 Unterschied zu `children`: `children` zeigt nur **Elemente**, keine Texte oder Kommentare.

---

## 🧠 Warum ist das wichtig?

- Nodes sind die **Basis** aller DOM-Operationen
- Wenn du z. B. whitespace oder Text mitlesen willst, brauchst du `childNodes`
- Auch für Vorlagen & Custom DOM-Bearbeitung wichtig

---

## ✅ Zusammenfassung

| Node-Konzept         | Beschreibung                             |
|-----------------------|------------------------------------------|
| `nodeType`            | Typ (z. B. 1 = Element, 3 = Text)        |
| `nodeName`            | Name des Elements (z. B. `DIV`)          |
| `nodeValue`           | Nur bei Text-, Attribut- und Kommentar-Nodes |
| `childNodes`          | Liste aller Kindknoten inkl. Text        |
| `textContent`         | Nur reiner Text                          |
