# 🔧 DOM – Elemente

## 🧩 Was ist ein DOM-Element?

Ein **Element** ist ein **Knoten im HTML-Baum**, der ein HTML-Tag repräsentiert (z. B. `<div>`, `<p>`, `<form>`).  
Mit JavaScript kannst du auf Elemente zugreifen und sie manipulieren: Inhalte, Attribute, CSS, Events u. v. m.

---

## 🛠 Zugriff auf Elemente

Typisch über:

```js
const element = document.querySelector("#meine-box");
```

---

## ✏️ Inhalt manipulieren

| Eigenschaft       | Beschreibung                                    |
|-------------------|-------------------------------------------------|
| `innerHTML`       | HTML-Inhalt als String lesen oder setzen        |
| `textContent`     | Nur Text ohne HTML                              |
| `innerText`       | Sichtbarer Text (mit Rücksicht auf CSS)         |

### Beispiel:

```js
element.innerHTML = "<strong>Fett!</strong>";
element.textContent = "Nur Text";
```

---

## 🎨 CSS-Eigenschaften setzen

```js
element.style.color = "red";
element.style.fontWeight = "bold";
element.style.backgroundColor = "#eee";
```

> Tipp: CSS-Namen mit Bindestrich werden zu camelCase → `font-size` → `fontSize`

---

## 🎯 Klassen verwalten

Nutze `classList` für moderne, einfache Klassennutzung:

```js
element.classList.add("aktiv");
element.classList.remove("unsichtbar");
element.classList.toggle("ausgewählt");
element.classList.contains("aktiv"); // true/false
```

---

## 📛 Attribute lesen und ändern

| Methode                        | Beschreibung                          |
|--------------------------------|----------------------------------------|
| `getAttribute("name")`         | Wert lesen                            |
| `setAttribute("name", "wert")` | Wert setzen                           |
| `removeAttribute("name")`      | Attribut entfernen                    |
| `hasAttribute("name")`         | Prüfen, ob Attribut existiert         |

### Beispiel:

```js
element.setAttribute("data-id", "42");
console.log(element.getAttribute("data-id")); // "42"
```

---

## 📎 Daten-Attribute (`data-*`)

```html
<div id="karte" data-user="florian"></div>
```

Zugriff mit:

```js
const karte = document.getElementById("karte");
console.log(karte.dataset.user); // "florian"
```

---

## 🧱 Elemente erstellen

```js
const neuerButton = document.createElement("button");
neuerButton.textContent = "Klick mich!";
neuerButton.classList.add("btn");

document.body.appendChild(neuerButton);
```

---

## 🧹 Elemente entfernen

```js
element.remove(); // Entfernt sich selbst
```

Alternativ:

```js
element.parentNode.removeChild(element);
```

---

## 🧪 Prüfung und Vergleich

```js
if (element.classList.contains("aktiv")) {
  console.log("Ist aktiv!");
}
```

---

## 🧠 Zusammenfassung

| Was du tun willst            | Methode/Eigenschaft                   |
|------------------------------|----------------------------------------|
| Inhalt lesen/schreiben       | `innerHTML`, `textContent`             |
| CSS direkt setzen            | `element.style.property`               |
| Klassen verwalten            | `classList.add()` usw.                 |
| Attribute manipulieren       | `get/set/removeAttribute()`            |
| Daten-Attribute nutzen       | `element.dataset.name`                 |
| Neues Element erzeugen       | `document.createElement("tag")`        |
| Einfügen oder entfernen      | `appendChild()`, `remove()`            |

