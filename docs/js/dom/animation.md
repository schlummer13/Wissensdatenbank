# 🎞️ DOM – Animationen & Übergänge

## 🧩 Was sind DOM-Animationen?

DOM-Animationen sind **visuelle Veränderungen von HTML-Elementen**, die über JavaScript gesteuert werden.  
Du kannst damit Elemente einblenden, bewegen, vergrößern, Farben wechseln – Schritt für Schritt oder flüssig.

> Es gibt zwei Hauptmethoden:  
> 👉 CSS-Übergänge (`transition`) + JavaScript  
> 👉 JavaScript-Animationen mit `setInterval`, `requestAnimationFrame` oder Web APIs

---

## 🎨 CSS-Animationen mit JavaScript auslösen

### 1. Element vorbereiten (CSS)

```css
.box {
  transition: transform 0.3s ease-in-out;
}

.box.verschoben {
  transform: translateX(200px);
}
```

### 2. JavaScript: Klasse ändern

```js
const box = document.querySelector(".box");
box.classList.toggle("verschoben");
```

🔁 Ergebnis: Box bewegt sich beim Klick!

---

## 🔁 CSS-Eigenschaften direkt animieren

```js
const el = document.querySelector(".box");

el.style.transition = "all 0.5s ease";
el.style.opacity = "0.3";
el.style.transform = "scale(1.2)";
```

---

## 🕒 JavaScript-Animation mit `setInterval`

```js
let pos = 0;
const box = document.getElementById("anim");

const timer = setInterval(() => {
  if (pos >= 300) {
    clearInterval(timer);
  } else {
    pos++;
    box.style.left = pos + "px";
  }
}, 10);
```

📌 Diese Methode ist einfach, aber weniger performant.

---

## 🚀 Modern: `requestAnimationFrame()`

```js
let x = 0;
const box = document.querySelector(".box");

function bewege() {
  x++;
  box.style.transform = `translateX(${x}px)`;

  if (x < 200) {
    requestAnimationFrame(bewege);
  }
}

bewege();
```

✅ Vorteil: Synchron mit Bildwiederholrate, stromsparend und ruckelfrei.

---

## 💥 Element einblenden

```js
const box = document.querySelector(".box");

box.style.opacity = "0";
box.style.transition = "opacity 0.5s";
box.style.opacity = "1"; // wird animiert eingeblendet
```

---

## 🔚 Animation beenden erkennen

```js
box.addEventListener("transitionend", () => {
  console.log("Animation abgeschlossen!");
});
```

---

## 📑 Beispiel: Farbe mit Übergang ändern

```html
<button id="knopf">Farbe ändern</button>
<div id="feld" style="width: 100px; height: 100px; background: blue; transition: background 0.5s;"></div>
```

```js
document.getElementById("knopf").addEventListener("click", () => {
  document.getElementById("feld").style.background = "tomato";
});
```

---

## ✅ Zusammenfassung

| Ziel                          | Methode                         |
|-------------------------------|----------------------------------|
| Ein-/Ausblenden               | `opacity`, `display`, `classList` |
| Bewegung                     | `transform`, `left/top`, CSS `transition` |
| JavaScript-Zeitsteuerung     | `setInterval`, `setTimeout`     |
| Performant animieren         | `requestAnimationFrame()`       |
| Animation beenden erkennen   | `transitionend`                 |

