# 🛠️ JavaScript DOM – Methoden

## 📌 Was sind DOM-Methoden?

DOM-Methoden sind **Funktionen**, mit denen du HTML-Elemente im Dokument **suchen, erstellen, ändern oder löschen** kannst.

> Du kannst dir DOM-Methoden wie Werkzeuge vorstellen, mit denen du live im HTML-Baum arbeiten kannst.

---

## 🔍 Elemente finden

| Methode                         | Beschreibung                               |
|----------------------------------|--------------------------------------------|
| `getElementById("id")`           | Findet ein Element mit einer ID            |
| `getElementsByClassName("class")`| Gibt HTMLCollection aller passenden Klassen |
| `getElementsByTagName("tag")`    | Gibt alle `<div>`, `<p>`, etc.             |
| `querySelector("selector")`      | Gibt **das erste** Element für CSS-Selector |
| `querySelectorAll("selector")`   | Gibt **alle** passenden Elemente (NodeList) |

### Beispiel

```js
const title = document.getElementById("main-title");
const alleAbsätze = document.querySelectorAll("p");
```

---

## 🧱 Elemente erstellen

| Methode                     | Beschreibung                            |
|-----------------------------|-------------------------------------------|
| `createElement("tag")`      | Erstellt ein neues HTML-Element          |
| `createTextNode("Text")`    | Erstellt einen reinen Textknoten         |
| `cloneNode(true/false)`     | Dupliziert ein Element                   |

### Beispiel

```js
const neuerAbsatz = document.createElement("p");
neuerAbsatz.textContent = "Ich bin neu!";
document.body.appendChild(neuerAbsatz);
```

---

## 🔁 Einfügen, Anhängen & Verschieben

| Methode                   | Beschreibung                                   |
|---------------------------|------------------------------------------------|
| `appendChild(node)`       | Hängt Knoten als **letztes Kind** an          |
| `insertBefore(neu, vor)`  | Fügt `neu` **vor** einem anderen Element ein  |
| `replaceChild(neu, alt)`  | Ersetzt vorhandenes Kind                      |
| `append()`, `prepend()`   | Fügt mehrere Nodes oder Text ein (modern!)    |

### Beispiel

```js
const ul = document.querySelector("ul");
const li = document.createElement("li");
li.textContent = "Neuer Eintrag";
ul.appendChild(li);
```

---

## 🗑️ Elemente entfernen

| Methode                 | Beschreibung                            |
|-------------------------|-------------------------------------------|
| `remove()`              | Entfernt sich selbst aus dem DOM         |
| `removeChild(child)`    | Entfernt Kindknoten von Elternelement     |

### Beispiel

```js
const element = document.querySelector(".hinweis");
element.remove(); // Entfernt sich selbst
```

---

## 🧠 Inhalt manipulieren

| Methode / Eigenschaft       | Beschreibung                                 |
|------------------------------|----------------------------------------------|
| `innerHTML`                 | Gibt HTML-Inhalt zurück oder setzt ihn       |
| `textContent`               | Gibt nur Text ohne HTML zurück               |
| `innerText`                 | Sichtbarer Text (wie auf der Seite sichtbar) |

### Beispiel

```js
element.innerHTML = "<strong>Fett!</strong>";
element.textContent = "Nur Text";
```

---

## 🎨 Attribute bearbeiten

| Methode                       | Beschreibung                      |
|-------------------------------|-----------------------------------|
| `setAttribute("name", "wert")`| Setzt ein Attribut                |
| `getAttribute("name")`        | Liest Attributwert                |
| `removeAttribute("name")`     | Entfernt Attribut                 |
| `hasAttribute("name")`        | Prüft, ob vorhanden               |

### Beispiel

```js
const link = document.querySelector("a");
link.setAttribute("target", "_blank");
```

---

## ✅ Klassen und Styles

```js
element.classList.add("aktiv");
element.classList.remove("inaktiv");
element.classList.toggle("sichtbar");

element.style.color = "red";
element.style.fontWeight = "bold";
```

---

## 📎 Strukturübersicht

```js
document
 └── html
     └── body
         └── div
             └── p
```

Mit DOM-Methoden kannst du in jeden Teil dieses Baumes **hineingreifen und ihn verändern**!

---

## 🧠 Tipp: `querySelector` ist der Allrounder

Du kannst damit **CSS-Selektoren direkt verwenden**:

```js
document.querySelector("ul > li.active");
document.querySelector("#header nav a:last-child");
```

---

## 🚀 Fazit

| Aktion             | Methode                           |
|--------------------|------------------------------------|
| Finden             | `querySelector`, `getElementById` |
| Erstellen          | `createElement`, `createTextNode` |
| Einfügen           | `appendChild`, `append`            |
| Entfernen          | `remove()`, `removeChild()`        |
| Inhalte bearbeiten | `innerHTML`, `textContent`         |
| Attribute ändern   | `setAttribute`, `getAttribute`     |
