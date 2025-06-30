# 🧱 Klassen (`class`)

Mit Klassen kannst du **Objektvorlagen** erstellen, die Eigenschaften (Daten) und Methoden (Funktionen) kombinieren. Sie helfen, deinen Code **strukturierter, wiederverwendbarer und objektorientiert** zu gestalten.

> Klassen wurden mit **ES6** (2015) eingeführt und sind syntaktischer Zucker über dem Prototypensystem von JavaScript.

---

## 📌 Grundstruktur einer Klasse

```js
class Auto {
  constructor(marke, ps) {
    this.marke = marke;
    this.ps = ps;
  }

  starten() {
    console.log(`${this.marke} startet mit ${this.ps} PS.`);
  }
}
```

---

## 🧪 Objekt aus Klasse erzeugen

```js
const meinAuto = new Auto("BMW", 200);
meinAuto.starten(); // BMW startet mit 200 PS.
```

> Du verwendest `new`, um ein neues **Instanz-Objekt** der Klasse zu erzeugen.

---

## 🔧 `constructor()` – Der Bauplan

- Die `constructor()`-Methode wird **automatisch** aufgerufen, wenn eine neue Instanz erzeugt wird.
- Sie dient zur **Initialisierung von Eigenschaften** (z. B. `this.name`).

---

## 🔁 Methoden in Klassen

Methoden sind einfach **Funktionen innerhalb einer Klasse**:

```js
class Rechner {
  addiere(x, y) {
    return x + y;
  }
}

const r = new Rechner();
console.log(r.addiere(2, 3)); // 5
```

---

## 🧠 `this` in Klassen

- Innerhalb einer Methode verweist `this` **auf die aktuelle Instanz**.
- Dadurch kannst du auf Eigenschaften und Methoden derselben Klasse zugreifen.

---

## 🧬 Vererbung mit `extends`

Du kannst eine Klasse von einer anderen **erben** lassen:

```js
class Tier {
  constructor(name) {
    this.name = name;
  }

  sprechen() {
    console.log(`${this.name} macht ein Geräusch.`);
  }
}

class Hund extends Tier {
  sprechen() {
    console.log(`${this.name} bellt.`);
  }
}

const rex = new Hund("Rex");
rex.sprechen(); // Rex bellt.
```

---

## 🔗 `super()` – Auf Elternklasse zugreifen

Wenn du von einer Klasse erbst, kannst du mit `super()` den **Konstruktor oder Methoden der Elternklasse** aufrufen:

```js
class Katze extends Tier {
  constructor(name) {
    super(name); // ruft Tier's constructor auf
  }
}
```

---

## 🔒 Private Eigenschaften (ab ES2022)

```js
class Benutzer {
  #passwort;

  constructor(name, passwort) {
    this.name = name;
    this.#passwort = passwort;
  }

  pruefen(pw) {
    return pw === this.#passwort;
  }
}

const u = new Benutzer("Anna", "geheim");
u.pruefen("geheim"); // true
u.#passwort; // ❌ Fehler: privat
```

---

## ⚙️ Static Methoden & Eigenschaften

- Gehören zur **Klasse**, nicht zur Instanz:

```js
class Mathe {
  static quadrieren(x) {
    return x * x;
  }
}

console.log(Mathe.quadrieren(5)); // 25
```

---

## 🧠 Klassen vs. Funktionen

| Aspekt            | Funktion                                  | Klasse                     |
|-------------------|-------------------------------------------|----------------------------|
| Syntax            | flexibel, traditionell                    | moderner, klarer           |
| Konstruktor       | beliebige Funktion                        | `constructor()`            |
| Vererbung         | über `prototype`                          | mit `extends`, `super()`   |
| Kapselung         | schwieriger                               | mit `#private` möglich     |

---

## 🔁 Mini-Beispiel: Bankkonto

```js
class Konto {
  constructor(name, saldo) {
    this.name = name;
    this.saldo = saldo;
  }

  einzahlen(betrag) {
    this.saldo += betrag;
  }

  anzeigen() {
    console.log(`${this.name} hat €${this.saldo}`);
  }
}

const konto = new Konto("Florian", 100);
konto.einzahlen(50);
konto.anzeigen(); // Florian hat €150
```

---

## ✅ Zusammenfassung

| Element         | Zweck                                               |
|------------------|------------------------------------------------------|
| `class`          | Neue Klasse definieren                              |
| `constructor()`  | Startwerte setzen                                   |
| `this`           | Aktuelle Instanz                                    |
| `extends`        | Vererbung von anderer Klasse                        |
| `super()`        | Zugriff auf Elternklasse                            |
| `static`         | Funktion gehört nicht zur Instanz                   |
| `#privat`        | Private Felder ab ES2022                            |
