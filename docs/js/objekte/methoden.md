# 🔧 Object Methods (Methoden)

**Methoden** sind Funktionen, die in einem Objekt gespeichert sind. Sie ermöglichen es dir, Verhalten (Funktionen) direkt mit Daten (Eigenschaften) zu verbinden.

---

## 📌 Was ist eine Methode?

Eine Methode ist einfach eine **Funktion als Eigenschaft** eines Objekts.

```js
const person = {
  name: "Florian",
  sagHallo: function() {
    console.log("Hallo, ich bin " + this.name);
  }
};

person.sagHallo(); // Hallo, ich bin Florian
```

---

## 🎯 Warum Methoden?

- Binden Verhalten direkt ans Objekt
- Nutzen `this`, um auf eigene Eigenschaften zuzugreifen
- Helfen, Objekte zu organisieren und wiederverwendbar zu machen

---

## ✨ Kurzschreibweise (ES6)

```js
const user = {
  name: "Anna",
  begruessung() {
    console.log(`Hallo, ${this.name}`);
  }
};

user.begruessung(); // Hallo, Anna
```

---

## 🧠 `this` in Methoden

`this` bezieht sich innerhalb einer Methode immer auf **das Objekt selbst**:

```js
const auto = {
  marke: "Tesla",
  starten() {
    console.log(`${this.marke} startet...`);
  }
};

auto.starten(); // Tesla startet...
```

---

## 🔁 Methoden aufrufen

```js
person.sagHallo();
user.begruessung();
```

---

## 🧱 Methoden können Parameter haben

```js
const rechner = {
  multiplizieren(a, b) {
    return a * b;
  }
};

console.log(rechner.multiplizieren(3, 4)); // 12
```

---

## 📦 Methoden können auch Methoden aufrufen

```js
const konto = {
  stand: 1000,
  einzahlen(betrag) {
    this.stand += betrag;
  },
  auszahlung(betrag) {
    if (betrag <= this.stand) {
      this.stand -= betrag;
    }
  },
  info() {
    console.log(`Kontostand: ${this.stand} €`);
  }
};

konto.einzahlen(500);
konto.auszahlung(200);
konto.info(); // Kontostand: 1300 €
```

---

## 🧰 Dynamisch Methoden hinzufügen

```js
const hund = {
  name: "Bello"
};

hund.bellen = function() {
  console.log(`${this.name} sagt: Wuff!`);
};

hund.bellen(); // Bello sagt: Wuff!
```

---

## 🔄 Methoden aus anderen Objekten übernehmen

```js
const mathTools = {
  verdoppeln(x) {
    return x * 2;
  }
};

const meinObjekt = {
  wert: 10,
  rechne: mathTools.verdoppeln
};

console.log(meinObjekt.rechne(5)); // 10
```

---

## ✅ Methoden vs. Funktionen

| Funktion                     | Methode                          |
|------------------------------|----------------------------------|
| Steht alleine                | Gehört zu einem Objekt           |
| `function sagHallo() {}`     | `objekt.sagHallo = function() {}` |
| Hat kein automatisches `this`| Nutzt `this` für das eigene Objekt |

---

## 🧪 Mini-Beispiel

```js
const spieler = {
  name: "Lena",
  punkte: 0,
  punkteHinzufügen(wert) {
    this.punkte += wert;
    console.log(`${this.name} hat jetzt ${this.punkte} Punkte.`);
  }
};

spieler.punkteHinzufügen(10);
// → Lena hat jetzt 10 Punkte.
```

---

## 📚 Weiterführend

- `this` und Bindung verstehen
- Arrow Functions in Objekten vermeiden (kein eigenes `this`)
- Methoden-Kette (method chaining)
- Prototypen und Klassen
