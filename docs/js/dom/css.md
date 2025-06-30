# 🎨 DOM – CSS verändern

## 🧩 Was kann JavaScript mit CSS machen?

Mit JavaScript kannst du:

- CSS-Klassen hinzufügen oder entfernen
- Einzelne CSS-Eigenschaften direkt setzen
- Stylesheets dynamisch laden oder ändern
- Inline-Styles manipulieren

> So wird deine Webseite **interaktiv** und **dynamisch gestaltet**, z. B. bei Klicks, Scrolls oder Animationen.

---

## 📦 CSS direkt über `style`

```js
const box = document.querySelector(".box");

box.style.backgroundColor = "lightblue";
box.style.border = "2px solid black";
box.style.padding = "1rem";
```

💡 CSS-Eigenschaften in JavaScript:  
`background-color` → `backgroundColor` (camelCase!)

---

## 🧰 Klassen managen mit `classList`

Die moderne und sichere Methode, um Klassen zu verwalten:

```js
box.classList.add("aktiv");
box.classList.remove("versteckt");
box.classList.toggle("aktiv");       // an/aus
box.classList.contains("aktiv");     // true/false
```

---

## 📑 Unterschied: `className` vs. `classList`

```js
box.className = "neu"; // ersetzt alle Klassen
box.classList.add("neu"); // fügt nur diese hinzu
```

---

## 🔄 CSS durch JavaScript ein-/ausschalten

```js
document.body.classList.toggle("dark-mode");
```

In CSS:

```css
.dark-mode {
  background: #000;
  color: #fff;
}
```

---

## 🎯 Dynamische Stylesheets laden

```js
const link = document.createElement("link");
link.rel = "stylesheet";
link.href = "dark.css";
document.head.appendChild(link);
```

---

## 🎯 Dynamisch generierte Styles (selten, aber möglich)

```js
const style = document.createElement("style");
style.textContent = `
  .hinweis {
    color: red;
    font-weight: bold;
  }
`;
document.head.appendChild(style);
```

---

## 🧪 Beispiel: Farbe bei Klick ändern

```html
<button id="farbWechsler">Farbe ändern</button>
<div id="box" style="width: 100px; height: 100px; background: gray;"></div>
```

```js
document.getElementById("farbWechsler").addEventListener("click", () => {
  const box = document.getElementById("box");
  box.style.backgroundColor = "tomato";
});
```

---

## ✅ Zusammenfassung

| Ziel                        | Methode/Eigenschaft               |
|-----------------------------|------------------------------------|
| CSS direkt setzen           | `element.style.eigenschaft`       |
| CSS-Klassen verwalten       | `classList.add/remove/toggle()`   |
| Klasse vollständig ändern   | `className = "..."`               |
| Stylesheet dynamisch laden  | `document.createElement("link")`  |
| Dynamische CSS einfügen     | `document.createElement("style")` |
