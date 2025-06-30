# 📐 Math (Mathematische Funktionen)

Das `Math`-Objekt in JavaScript stellt dir viele **mathematische Funktionen und Konstanten** zur Verfügung – von Rundungen und Zufallszahlen bis zu Trigonometrie und Potenzen.

> `Math` ist **kein Konstruktor** – du musst es **nicht mit `new` verwenden**.

---

## 📌 Grundlegende Verwendung

```js
Math.PI           // 3.14159...
Math.E            // Eulersche Zahl ≈ 2.718
Math.SQRT2        // √2
Math.LN2          // natürlicher Logarithmus von 2
```

---

## 🔢 Rundungsfunktionen

| Methode            | Beschreibung                            | Beispiel            |
|--------------------|-----------------------------------------|---------------------|
| `Math.round(x)`    | Rundet **auf/ab** (normal)              | `Math.round(4.6)` → `5` |
| `Math.floor(x)`    | Rundet **ab**                           | `Math.floor(4.9)` → `4` |
| `Math.ceil(x)`     | Rundet **auf**                          | `Math.ceil(4.1)` → `5` |
| `Math.trunc(x)`    | Entfernt Nachkommastellen               | `Math.trunc(4.9)` → `4` |

---

## 🎲 Zufallszahlen

```js
Math.random(); // Zahl zwischen 0 (inkl.) und 1 (exkl.)
```

### 🧩 Zufallszahl in bestimmtem Bereich

```js
function zufall(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

zufall(1, 10); // z. B. 7
```

---

## ➕ Rechnen

| Methode              | Beschreibung                        |
|----------------------|-------------------------------------|
| `Math.max(a, b, …)`  | Größter Wert                        |
| `Math.min(a, b, …)`  | Kleinster Wert                      |
| `Math.abs(x)`        | Absoluter Betrag                    |
| `Math.pow(x, y)`     | Potenz (x hoch y)                   |
| `Math.sqrt(x)`       | Quadratwurzel                       |
| `Math.cbrt(x)`       | Kubikwurzel                         |
| `Math.sign(x)`       | -1, 0 oder 1 je nach Vorzeichen     |
| `Math.hypot(x, y)`   | √(x² + y²), z. B. für Vektoren      |

---

## 📐 Trigonometrie

Alle Winkelangaben in **Radiant** (nicht Grad!)

```js
Math.sin(x);   // Sinus
Math.cos(x);   // Kosinus
Math.tan(x);   // Tangens
Math.asin(x);  // Arkussinus (umgekehrte Funktion)
```

### Grad in Radiant umrechnen:

```js
function degToRad(deg) {
  return deg * (Math.PI / 180);
}

Math.sin(degToRad(90)); // ≈ 1
```

---

## 🧮 Logarithmen & Exponentialfunktionen

| Methode           | Bedeutung                          |
|-------------------|-------------------------------------|
| `Math.log(x)`     | natürlicher Logarithmus (Basis e)   |
| `Math.log10(x)`   | Logarithmus zur Basis 10            |
| `Math.exp(x)`     | e hoch x                            |

---

## 🧠 Beispiel: Kreisfläche berechnen

```js
function kreisFlaeche(radius) {
  return Math.PI * radius * radius;
}

console.log(kreisFlaeche(5)); // ≈ 78.54
```

---

## 🔄 Werte begrenzen (Clamping)

```js
function clamp(value, min, max) {
  return Math.max(min, Math.min(max, value));
}

clamp(120, 0, 100); // → 100
```

---

## ✅ Zusammenfassung

| Aufgabe              | Methode                            |
|----------------------|-------------------------------------|
| Runden               | `round()`, `floor()`, `ceil()`     |
| Zufallswert          | `random()`                          |
| Betrag               | `abs()`                             |
| Potenz / Wurzel      | `pow()`, `sqrt()`, `cbrt()`         |
| Maximum / Minimum    | `max()`, `min()`                    |
| Trigonometrie        | `sin()`, `cos()`, `tan()`           |
| Logarithmus / Exponential | `log()`, `exp()`               |

