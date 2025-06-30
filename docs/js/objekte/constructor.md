# 🏗️ Object Constructors

**Constructor Functions** sind spezielle Funktionen, mit denen du **mehrere Objekte mit derselben Struktur und Logik** erstellen kannst. Sie sind ein zentrales Konzept der objektorientierten Programmierung in JavaScript.

---

## 📌 Was ist ein Konstruktor?

Ein **Konstruktor** ist einfach eine normale Funktion, die:

- mit einem **Großbuchstaben** beginnt (Konvention)
- mit dem **`new`-Schlüsselwort** aufgerufen wird
- über `this` Eigenschaften und Methoden zuweist

---

## 🧱 Beispiel: Ein einfacher Konstruktor

```js
function Person(name, alter) {
  this.name = name;
  this.alter = alter;
  this.begruessung = function() {
    console.log(`Hallo, ich bin ${this.name} und ${this.alter} Jahre alt.`);
  };
}
```

➡️ Jetzt kannst du neue Personen erzeugen:

```js
const anna = new Person("Anna", 28);
const tom = new Person("Tom", 35);

anna.begruessung(); // Hallo, ich bin Anna...
tom.begruessung();  // Hallo, ich bin Tom...
```

---

## 🎯 Was macht `new`?

```js
const objekt = new Konstruktor();
```

- Erstellt ein **leeres Objekt**
- Setzt `this` in der Funktion auf dieses neue Objekt
- Führt den Funktionscode aus
- Gibt das Objekt zurück

---

## 🧠 Warum Konstruktoren?

- Wiederverwendbare Objektvorlagen
- Struktur & Verhalten definieren
- Basis für **Klassen** und **Vererbung**

---

## 🧰 Methoden auslagern (auf das Prototype)

Wenn du viele Objekte erstellst, ist es effizienter, Methoden **nicht im Objekt**, sondern auf dem **Prototyp** zu definieren:

```js
function Auto(marke) {
  this.marke = marke;
}

Auto.prototype.fahren = function() {
  console.log(`${this.marke} fährt los!`);
};

const bmw = new Auto("BMW");
bmw.fahren(); // BMW fährt los!
```

✅ Spart Speicher, weil alle Instanzen dieselbe Methode teilen.

---

## 🧪 Vergleich: Objektliterale vs. Konstruktoren

| Objektliteral                  | Konstruktorfunktion              |
|-------------------------------|----------------------------------|
| Für 1 Objekt                  | Für viele ähnliche Objekte       |
| Schnell und direkt            | Flexibel und wiederverwendbar    |
| Kein `new` nötig              | Wird mit `new` aufgerufen        |

---

## 🔐 Konstruktor-Erkennung

```js
console.log(bmw.constructor === Auto); // true
```

---

## 💡 Spezialtipp: `instanceof`

```js
console.log(bmw instanceof Auto); // true
```

---

## 📚 Beispiel mit mehreren Methoden

```js
function Tier(name, art) {
  this.name = name;
  this.art = art;
}

Tier.prototype.sprechen = function() {
  console.log(`${this.name} macht Geräusche.`);
};

const hund = new Tier("Bello", "Hund");
hund.sprechen(); // Bello macht Geräusche.
```

---

## ⚠️ Wichtige Hinweise

- Innerhalb des Konstruktors zeigt `this` auf das neue Objekt
- Wenn du den Konstruktor **ohne `new`** aufrufst, funktioniert er nicht richtig
- Ab ES6 gibt es auch `class`-Syntax als Alternative (siehe nächstes Kapitel)

