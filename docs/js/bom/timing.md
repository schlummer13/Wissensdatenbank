# ⏱️ BOM – Timing (setTimeout, setInterval, etc.)

## 🧩 Was ist "Timing" in JavaScript?

JavaScript erlaubt es dir, Funktionen **verzögert auszuführen** oder **wiederholt** aufzurufen.  
Das ist nützlich für z. B. Animationen, Countdown-Timer, Ladeverzögerungen oder automatische Updates.

---

## 🧮 Übersicht der Timer-Funktionen

| Methode           | Beschreibung                                |
|------------------|----------------------------------------------|
| `setTimeout()`   | Führt Code **einmalig verzögert** aus        |
| `setInterval()`  | Führt Code **wiederholt in Intervallen** aus |
| `clearTimeout()` | Bricht `setTimeout()` vorzeitig ab           |
| `clearInterval()`| Bricht `setInterval()` vorzeitig ab          |

---

## ✅ `setTimeout()` – Verzögerte Ausführung

```js
setTimeout(() => {
  console.log("Nach 2 Sekunden!");
}, 2000);
```

- Wird nur **einmal** ausgeführt
- Zeitangabe in **Millisekunden** (1000 ms = 1 Sekunde)

📦 Rückgabe ist eine Timer-ID (Zahl)

```js
const timerId = setTimeout(() => {
  console.log("Wird nicht ausgeführt");
}, 3000);

clearTimeout(timerId); // Bricht den Timer ab
```

---

## 🔁 `setInterval()` – Wiederholte Ausführung

```js
const intervallId = setInterval(() => {
  console.log("Jede Sekunde");
}, 1000);

// Stoppen nach 5 Sekunden:
setTimeout(() => {
  clearInterval(intervallId);
  console.log("Stopp");
}, 5000);
```

---

## 📌 Wichtige Hinweise

- Timer sind **asynchron** → blockieren den Hauptthread nicht
- Mehrere Timer können **parallel laufen**
- Genauer Zeitpunkt ist **nicht garantiert** (Verzögerungen durch CPU, Events etc.)
- Verwende `clearTimeout()` oder `clearInterval()`, um Ressourcen zu sparen

---

## 🧪 Beispiel: Countdown mit `setInterval`

```js
let count = 5;
const interval = setInterval(() => {
  console.log(count);
  count--;

  if (count < 0) {
    clearInterval(interval);
    console.log("Fertig!");
  }
}, 1000);
```

---

## ✅ Zusammenfassung

| Was du tun willst                | Methode                    |
|----------------------------------|-----------------------------|
| Code später einmal ausführen     | `setTimeout()`              |
| Code regelmäßig wiederholen      | `setInterval()`             |
| Laufenden Timeout abbrechen      | `clearTimeout(timeoutId)`   |
| Laufenden Intervall abbrechen    | `clearInterval(intervalId)` |

