# 🎧 DOM – Event Listener

## 🧩 Was ist ein Event Listener?

Ein **Event Listener** (Ereignis-Zuhörer) ist eine Funktion, die auf ein bestimmtes Ereignis wartet – z. B. „Klick“ oder „Eingabe“.  
Wenn das Ereignis eintritt, wird die zugehörige **Callback-Funktion** ausgeführt.

---

## ✅ Syntax

```js
element.addEventListener(eventTyp, callback, optionen);
```

| Teil             | Beschreibung                                       |
|------------------|----------------------------------------------------|
| `eventTyp`       | z. B. `"click"`, `"input"`, `"submit"`             |
| `callback`       | Funktion, die beim Event aufgerufen wird           |
| `optionen`       | Optional: z. B. `{ once: true }`, `{ passive: true }` |

---

## 📌 Beispiel: Klick auf Button

```js
const button = document.querySelector("button");

button.addEventListener("click", () => {
  alert("Button wurde geklickt!");
});
```

---

## 🔁 Einmaliger Listener (`once`)

```js
button.addEventListener("click", () => {
  alert("Nur einmal!");
}, { once: true });
```

✔️ Der Listener entfernt sich nach der ersten Ausführung selbst.

---

## 🧪 Beispiel: Eingabe beobachten

```js
const input = document.querySelector("input");

input.addEventListener("input", (e) => {
  console.log("Aktueller Wert:", e.target.value);
});
```

---

## 🔄 Entfernen eines Event Listeners

Du musst dieselbe Funktion-Referenz verwenden:

```js
function handleClick() {
  alert("Hallo");
}

button.addEventListener("click", handleClick);
button.removeEventListener("click", handleClick);
```

> Anonyme Funktionen können **nicht** entfernt werden!

---

## 🧠 Mehrere Listener für ein Element

```js
const box = document.querySelector(".box");

box.addEventListener("mouseenter", () => box.classList.add("aktiv"));
box.addEventListener("mouseleave", () => box.classList.remove("aktiv"));
```

---

## 🛑 Unterschied: inline `onclick` vs. `addEventListener`

| Methode              | Nachteile                                     |
|----------------------|-----------------------------------------------|
| `onclick = ...`      | Überschreibt andere Handler                   |
| `addEventListener()` | Besser, erlaubt mehrere Listener, mehr Kontrolle |

---

## ⚙️ Optionen für Event Listener

| Option     | Wirkung                                                  |
|------------|-----------------------------------------------------------|
| `once`     | Führt Listener nur einmal aus                            |
| `capture`  | Listener wird in der Capture-Phase ausgelöst             |
| `passive`  | Browser darf Event nicht blockieren (z. B. bei `scroll`) |

```js
element.addEventListener("scroll", handleScroll, { passive: true });
```

---

## 🧠 Event Delegation

Ein einziger Listener für viele Elemente – besonders effizient bei dynamischen Inhalten.

```js
document.querySelector("ul").addEventListener("click", (e) => {
  if (e.target.tagName === "LI") {
    e.target.classList.toggle("markiert");
  }
});
```

---

## ✅ Zusammenfassung

| Aktion                    | Methode / Konzept                       |
|---------------------------|------------------------------------------|
| Listener hinzufügen       | `addEventListener("event", fn)`         |
| Listener entfernen        | `removeEventListener("event", fn)`      |
| Nur 1× ausführen          | `{ once: true }`                        |
| Event delegation          | Parent fängt Event ab                   |
| Infos aus Event           | `event`, `event.target`                 |

