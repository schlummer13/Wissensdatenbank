# 🔧 Funktionen

**Funktionen** sind Bausteine in JavaScript, mit denen du Code **einmal schreibst** und **immer wieder verwenden** kannst. Sie helfen, dein Programm übersichtlicher und modularer zu gestalten.

---

## 📌 Was ist eine Funktion?

Eine Funktion ist ein Stück Code, das einen bestimmten Zweck erfüllt. Du kannst ihr **einen Namen geben**, **Daten übergeben (Parameter)** und bekommst bei Bedarf **ein Ergebnis zurück**.

### ▶️ Beispiel:

```js
function sagHallo() {
  console.log("Hallo Welt!");
}

sagHallo(); // → Gibt "Hallo Welt!" in der Konsole aus
```

---

## 🧱 Arten von Funktionen

### 1️⃣ **Funktions-Deklaration**

```js
function addiere(a, b) {
  return a + b;
}

console.log(addiere(2, 3)); // 5
```

- Beginnt mit dem Wort `function`
- Du kannst sie auch **vor ihrer Definition** benutzen (Hoisting)

---

### 2️⃣ **Funktions-Ausdruck (Expression)**

```js
const begruessung = function(name) {
  return `Hallo, ${name}`;
};

console.log(begruessung("Florian"));
```

- Funktion wird **einer Variable** zugewiesen
- Erst verfügbar, **nachdem sie im Code erscheint**

---

### 3️⃣ **Pfeilfunktion (Arrow Function)**

```js
const quadrat = (x) => x * x;
```

Oder ausführlicher:

```js
const begruessung = (name) => {
  return `Hallo, ${name}`;
};
```

- Kurzschreibweise
- Sehr beliebt für kurze Funktionen
- Achtung: Hat kein eigenes `this`

---

### 4️⃣ **Anonyme Funktion**

Eine Funktion ohne Namen, z. B. für Zeitverzögerungen:

```js
setTimeout(function() {
  console.log("Wird nach 1 Sekunde ausgeführt");
}, 1000);
```

---

## 🔁 Parameter & Rückgabewerte

Funktionen können **Werte entgegennehmen** (Parameter) und mit `return` einen **Wert zurückgeben**.

```js
function multipliziere(a, b) {
  return a * b;
}

let ergebnis = multipliziere(4, 5); // → 20
```

---

## 🧮 Standardwerte (Default-Parameter)

Falls kein Wert übergeben wird, greift ein **Standardwert**:

```js
function begruessung(name = "Gast") {
  console.log(`Willkommen, ${name}!`);
}

begruessung();           // Willkommen, Gast!
begruessung("Anna");     // Willkommen, Anna!
```

---

## 📦 Rest-Parameter (beliebig viele Argumente)

```js
function summe(...zahlen) {
  return zahlen.reduce((a, b) => a + b);
}

summe(1, 2, 3); // → 6
```

- Mit `...` kannst du **beliebig viele Werte** sammeln

---

## 🧪 Callback-Funktionen

Eine Funktion **wird als Argument an eine andere Funktion übergeben**:

```js
function verarbeite(callback) {
  console.log("Start");
  callback();
  console.log("Ende");
}

verarbeite(() => console.log("Ich bin der Callback"));
```

---

## 🧠 Funktionen = Werte

Funktionen können:

- In Variablen gespeichert werden
- An andere Funktionen übergeben werden
- Von Funktionen zurückgegeben werden

Das macht JavaScript extrem flexibel.

---

## 🔄 Rekursion – Funktion ruft sich selbst auf

```js
function fakultaet(n) {
  if (n <= 1) return 1;
  return n * fakultaet(n - 1);
}

console.log(fakultaet(5)); // → 120
```

💡 Wird verwendet, um **Schritte zu wiederholen**, z. B. bei Bäumen oder mathematischen Aufgaben.

---

## 🛠️ IIFE – sofort ausgeführte Funktion

```js
(function() {
  console.log("Ich starte direkt!");
})();
```

- Praktisch, wenn man **einmaligen Code** ausführen will
- Auch nützlich, um **Variablen privat** zu halten

---

## 📘 Funktionen vs. Methoden

```js
function globalFunktion() {
  return "Ich bin global";
}

const person = {
  name: "Florian",
  begruessung() {
    return `Hallo ${this.name}`;
  }
};
```

- **Funktion**: unabhängig
- **Methode**: gehört zu einem Objekt
