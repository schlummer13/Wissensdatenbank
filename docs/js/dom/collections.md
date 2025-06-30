# 📚 JavaScript DOM – NodeLists & HTMLCollections

## 🧩 Was sind NodeLists & HTMLCollections?

Wenn du mehrere DOM-Elemente auswählst, bekommst du **spezielle Listen** zurück:

- **NodeList** → Ergebnis von `querySelectorAll()`  
- **HTMLCollection** → Ergebnis von z. B. `getElementsByClassName()`

Beides sieht aus wie ein Array, **ist aber kein echtes Array!**

---

## 🔍 NodeList

```js
const absätze = document.querySelectorAll("p");
console.log(absätze); // NodeList
```

- Enthält alle passenden Knoten (meist `Element`)
- Kann mit `.forEach()` durchlaufen werden
- Ist **statisch** (ändert sich nicht automatisch bei DOM-Änderungen)

---

## 🧪 Beispiel: NodeList iterieren

```js
document.querySelectorAll("li").forEach((li) => {
  li.style.color = "blue";
});
```

---

## 📦 HTMLCollection

```js
const elemente = document.getElementsByTagName("p");
console.log(elemente); // HTMLCollection
```

- Ähnlich wie NodeList
- Aber: **live** – aktualisiert sich, wenn sich das DOM ändert
- Hat **kein `.forEach()`** – muss konvertiert werden

---

## 🔁 HTMLCollection in Array umwandeln

```js
const collection = document.getElementsByClassName("box");

// Variante 1
const array1 = Array.from(collection);

// Variante 2
const array2 = [...collection];

array2.forEach(el => el.style.background = "lightgray");
```

---

## ⚠️ Unterschiede im Überblick

| Eigenschaft              | NodeList                    | HTMLCollection              |
|--------------------------|------------------------------|-----------------------------|
| Herkunft                 | `querySelectorAll()`         | `getElementsBy*()`          |
| Inhalt                   | Knoten (meist Elemente)      | Nur HTML-Elemente           |
| live / statisch          | **statisch**                 | **live** (aktualisiert sich)|
| `forEach()`              | ✅ (direkt nutzbar)           | ❌ (muss konvertiert werden)|
| Zugriff mit Index        | ✅                           | ✅                           |

---

## ✅ Wann was verwenden?

| Situation                          | Empfohlene Methode         |
|------------------------------------|-----------------------------|
| Einfache CSS-ähnliche Auswahl      | `querySelectorAll()` (NodeList) |
| Alte APIs, Performance entscheidend| `getElementsByClassName()` (HTMLCollection) |

---

## 🧠 Warum ist das wichtig?

- Für dynamische Anwendungen musst du wissen, ob sich die Liste **automatisch aktualisiert**
- Viele Methoden liefern NodeLists – aber oft brauchst du Array-Methoden → **umwandeln!**

---

## 🚀 Bonus: Livesichtbarkeit testen

```js
const list = document.getElementsByTagName("li");

console.log(list.length); // z. B. 3

const neuerEintrag = document.createElement("li");
neuerEintrag.textContent = "Neu";
document.querySelector("ul").appendChild(neuerEintrag);

console.log(list.length); // jetzt 4 → HTMLCollection ist live!
```

---

## ✅ Zusammenfassung

| Punkt             | NodeList              | HTMLCollection         |
|-------------------|------------------------|-------------------------|
| Statisch          | ✅                     | ❌ (live)               |
| `forEach()`       | ✅                     | ❌                     |
| Konvertierbar     | ✅                     | ✅                     |
| DOM-kompatibel    | ✅                     | ✅                     |

---

🎉 Glückwunsch – du kennst jetzt die komplette Basis des **DOM-Zugriffs in JavaScript**!

---

> Nächste Themen könnten sein: **MutationObserver**, **Shadow DOM**, oder du steigst direkt in **Frameworks** wie React oder Vue ein!