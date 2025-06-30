# 🖱️ DOM – Events

## 🧩 Was ist ein Event?

Ein **Event** (deutsch: Ereignis) ist etwas, das im Browser passiert – z. B. ein Klick, eine Tasteneingabe oder das Laden der Seite.  
Mit JavaScript kannst du auf solche Ereignisse **reagieren**, z. B. mit einer Funktion.

---

## 🔔 Beispiele für Events

| Event           | Wann es passiert                        |
|------------------|-----------------------------------------|
| `click`          | Nutzer klickt auf ein Element           |
| `input`          | Nutzer gibt Text ein                    |
| `submit`         | Formular wird abgeschickt               |
| `change`         | Eingabefeld ändert sich (z. B. Dropdown)|
| `mouseover`      | Maus geht über ein Element              |
| `mouseout`       | Maus verlässt ein Element               |
| `keydown`        | Taste wird gedrückt                     |
| `load`           | Seite oder Bild ist komplett geladen    |
| `scroll`         | Benutzer scrollt auf der Seite          |
| `resize`         | Fenstergröße verändert sich             |

---

## 📌 Event-Handler (klassisch)

```js
const button = document.querySelector("button");

button.onclick = function () {
  alert("Du hast geklickt!");
};
```

⚠️ Achtung: Nur **ein Handler** möglich, der letzte überschreibt vorherige.

---

## ✅ Modern: `addEventListener`

```js
button.addEventListener("click", () => {
  alert("Hallo von addEventListener!");
});
```

✔️ Vorteil: Mehrere Listener möglich, sauber & flexibel.

---

## 🧪 Beispiel: Event bei Texteingabe

```js
const input = document.querySelector("input");

input.addEventListener("input", function () {
  console.log("Eingegeben: " + input.value);
});
```

---

## 🧠 Event-Objekt

Jedes Event löst automatisch ein **Event-Objekt** aus:

```js
button.addEventListener("click", function (event) {
  console.log(event); // Infos über das Event
  console.log(event.target); // Das angeklickte Element
});
```

---

## 🛑 `preventDefault()`

Verhindert Standardverhalten (z. B. das Abschicken eines Formulars):

```js
form.addEventListener("submit", function (e) {
  e.preventDefault();
  alert("Formular wurde NICHT abgeschickt");
});
```

---

## 🔄 `stopPropagation()`

Verhindert, dass ein Event weiter „blubbert“ (Bubble Phase):

```js
innerDiv.addEventListener("click", (e) => {
  e.stopPropagation();
});
```

---

## 📑 Mehrere Listener an einem Element

```js
const box = document.querySelector(".box");

box.addEventListener("mouseenter", () => box.classList.add("hovered"));
box.addEventListener("mouseleave", () => box.classList.remove("hovered"));
```

---

## ✅ Zusammenfassung

| Ziel                          | Methode                      |
|-------------------------------|-------------------------------|
| Event zuweisen                | `addEventListener()`          |
| Infos über das Ereignis       | `event`, `event.target`       |
| Standardverhalten verhindern  | `event.preventDefault()`      |
| Weitergabe stoppen            | `event.stopPropagation()`     |
