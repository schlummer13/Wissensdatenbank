# 📘 DOM – Einführung

## 🧩 Was ist das DOM?

**DOM** steht für **Document Object Model**.  
Es ist eine programmatische **Darstellung deiner HTML-Webseite als Baumstruktur**, mit der JavaScript Inhalte **lesen, verändern, hinzufügen oder löschen** kann.

> Kurz gesagt: **Mit dem DOM kannst du HTML mit JavaScript beeinflussen.**

---

## 🌳 So sieht das DOM aus

HTML wird im Browser als **Baum aus Knoten (Nodes)** dargestellt:

```html
<html>
  <head>
    <title>Beispiel</title>
  </head>
  <body>
    <h1>Hallo Welt</h1>
    <p>Ein Absatz</p>
  </body>
</html>
```

Wird zu:

```
document
 └── html
     ├── head
     │   └── title
     └── body
         ├── h1
         └── p
```

---

## 📦 Was kann man mit dem DOM machen?

| Aufgabe                     | Beispielcode                           |
|-----------------------------|-----------------------------------------|
| Inhalte lesen               | `document.querySelector("p").textContent` |
| Inhalte verändern           | `element.innerHTML = "Neu"`             |
| Elemente erstellen          | `document.createElement("div")`         |
| Elemente entfernen          | `element.remove()`                      |
| CSS ändern                  | `element.style.color = "red"`           |
| Events hinzufügen           | `element.addEventListener("click", ...)` |

---

## 🛠 Warum ist das DOM wichtig?

- Macht deine Webseite **interaktiv**
- Ermöglicht **dynamisches Nachladen** von Inhalten
- Wird von **JavaScript gesteuert**
- Basis für **Webanwendungen** (z. B. To-do-Apps, Spiele, Formulare)

---

## 🧠 Wie greift man auf das DOM zu?

Im Browser ist das `document`-Objekt der Einstiegspunkt:

```js
console.log(document.title);         // Gibt den Titel der Seite aus
console.log(document.body.innerHTML); // Gibt den HTML-Inhalt des Body aus
```

---

## 🚀 DOM = Basis für alles Dynamische

Ohne DOM gäbe es nur **statisches HTML**.  
Mit DOM + JavaScript werden Webseiten:

- **Lebendig**
- **Anpassbar**
- **Reaktiv**

---

## 📚 Themenübersicht

In den nächsten Abschnitten lernst du alles über:

1. **DOM-Methoden**
2. **document**-Objekt
3. **HTML-Elemente bearbeiten**
4. **Formulare & CSS**
5. **DOM-Animationen**
6. **DOM-Events & Listener**
7. **Node-Navigation**
8. **Collections vs. NodeLists**

Bleib dran! 💡