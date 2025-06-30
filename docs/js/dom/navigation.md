# 🧭 DOM – Navigation durch den DOM-Baum

## 🧩 Was ist DOM-Navigation?

DOM-Navigation bedeutet, dass du dich **durch die Struktur des HTML-Dokuments bewegst**, um Elemente zu finden oder zu verändern.

> Du kannst z. B. von einem Element zum übergeordneten (`parent`), nächsten (`next`) oder enthaltenen (`child`) Element navigieren.

---

## 📑 Beispielstruktur

```html
<div id="eltern">
  <p id="kind1">Erstes Kind</p>
  <p id="kind2">Zweites Kind</p>
</div>
```

---

## 🔼 `parentNode` / `parentElement`

Gibt das **übergeordnete** Element zurück:

```js
const kind = document.getElementById("kind1");
console.log(kind.parentNode);     // <div id="eltern">
```

- `parentElement` = wie `parentNode`, aber garantiert ein HTML-Element

---

## 🔽 `childNodes` & `children`

```js
const eltern = document.getElementById("eltern");

console.log(eltern.childNodes); // Alle Knoten (inkl. Text!)
console.log(eltern.children);   // Nur HTML-Elemente
```

- `children` ist oft praktischer, weil es nur echte Tags enthält

---

## 🔁 `firstChild`, `lastChild` vs. `firstElementChild`

```js
eltern.firstChild           // erster Knoten (z. B. Text oder Element)
eltern.firstElementChild    // erstes HTML-Element
eltern.lastElementChild     // letztes HTML-Element
```

---

## ↔️ Geschwister: `nextSibling`, `previousSibling`

```js
const kind = document.getElementById("kind1");

console.log(kind.nextSibling);         // nächster Knoten (Text oder Tag)
console.log(kind.nextElementSibling);  // nächstes HTML-Element
```

```js
console.log(kind.previousElementSibling); // vorheriges HTML-Element
```

---

## 🔎 Nützliche Navigation auf einen Blick

| Zugriff                    | Beschreibung                            |
|----------------------------|------------------------------------------|
| `parentNode`               | Direktes Elternelement                   |
| `childNodes` / `children`  | Alle bzw. nur Element-Kinder             |
| `firstChild`               | Erster Kind-Knoten (auch Text!)         |
| `firstElementChild`        | Erstes Kind-Element                      |
| `nextElementSibling`       | Nächstes Geschwisterelement              |
| `previousElementSibling`   | Vorheriges Geschwisterelement            |

---

## 🧪 Beispiel: Farbe des nächsten Elements ändern

```js
const aktuelles = document.getElementById("kind1");

aktuelles.nextElementSibling.style.color = "tomato";
```

---

## 🧠 Warum ist das wichtig?

- Du kannst gezielt mit „Verwandten“ im HTML arbeiten
- Macht Code flexibel und dynamisch
- Wichtig für DOM-Manipulation, Events, Templates