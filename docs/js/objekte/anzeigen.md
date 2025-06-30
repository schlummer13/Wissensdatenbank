# 🖥️ Objekte anzeigen (Object Display)

Wenn du mit Objekten arbeitest, möchtest du oft sehen, **was drin steckt**. Es gibt verschiedene Möglichkeiten, ein Objekt in JavaScript **sichtbar zu machen**, zu inspizieren oder formatiert auszugeben – besonders beim Debugging.

---

## 🔍 1. `console.log(objekt)`

```js
const person = { name: "Anna", alter: 30 };
console.log(person);
```

✅ Zeigt das Objekt direkt in der Konsole.  
👉 In modernen Browsern kannst du das Objekt **aufklappen**, um Details zu sehen.

---

## 🔎 2. `console.dir(objekt)`

```js
console.dir(person);
```

Zeigt eine interaktive Objektansicht – besonders nützlich für HTML-DOM-Elemente.

---

## 🧾 3. JSON-Format: `JSON.stringify()`

```js
console.log(JSON.stringify(person));
// → {"name":"Anna","alter":30}
```

💡 Optional: **Einrücken für bessere Lesbarkeit**:

```js
console.log(JSON.stringify(person, null, 2));
```

Ergebnis:

```json
{
  "name": "Anna",
  "alter": 30
}
```

---

## 🎨 4. HTML-Ausgabe

Möchtest du ein Objekt **in einer Webseite anzeigen**, kannst du es wie folgt einbinden:

```html
<pre id="ausgabe"></pre>

<script>
  const person = { name: "Tom", alter: 28 };
  document.getElementById("ausgabe").textContent = JSON.stringify(person, null, 2);
</script>
```

💡 `<pre>` sorgt für Zeilenumbrüche und Einrückung.

---

## 📋 5. Alle Eigenschaften auflisten

```js
const obj = { a: 1, b: 2 };

console.log(Object.keys(obj));    // ["a", "b"]
console.log(Object.values(obj));  // [1, 2]
console.log(Object.entries(obj)); // [["a",1],["b",2]]
```

---

## 🧪 6. Manuelles Auslesen

```js
for (let key in obj) {
  console.log(`${key}: ${obj[key]}`);
}
```

---

## 🚫 7. Vorsicht bei zirkulären Objekten

Ein Objekt, das auf sich selbst verweist, kann `JSON.stringify()` zum Absturz bringen:

```js
const kreis = {};
kreis.selbst = kreis;

JSON.stringify(kreis); // ❌ TypeError: Converting circular structure to JSON
```

✅ Lösung mit spezieller Bibliothek wie `circular-json` oder `structuredClone()` (ab neueren Browsern).

---

## 🧰 Nützliche Tools (Dev Tools)

- Browser-Konsole (Chrome, Firefox, Edge)
- Breakpoints im Debugger
- Watch- oder Scope-Fenster in Entwicklertools

---

## 📚 Zusammenfassung

| Methode                    | Beschreibung                                |
|----------------------------|---------------------------------------------|
| `console.log(obj)`         | Einfacher Konsolenausdruck                  |
| `console.dir(obj)`         | Interaktive Darstellung                     |
| `JSON.stringify(obj)`      | Objekt als Text (z. B. für API oder Debug) |
| `Object.keys/values/entries` | Strukturiertes Auslesen                  |
| `for...in`                 | Manuelles Durchlaufen                      |

