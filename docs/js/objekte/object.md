# 📦 Objekte

**Objekte** sind eine der wichtigsten Strukturen in JavaScript. Mit ihnen kannst du **Daten bündeln**, **Eigenschaften speichern** und **Funktionen** (sogenannte Methoden) zu Gruppen zusammenfassen.

---

## 📌 Was ist ein Objekt?

Ein Objekt besteht aus **Eigenschaften (Werte)** und **Methoden (Funktionen)**, die unter einem gemeinsamen Namen organisiert sind.  
Ein Objekt ist wie eine Art **„Datenpaket“**, das zu einer bestimmten Sache gehört.

---

## 🧱 Objekt erstellen

### 🔹 1. Mit geschweiften Klammern (`{}`)

```js
const person = {
  vorname: "Max",
  nachname: "Mustermann",
  alter: 30,
  istAktiv: true
};
```

---

### 🔹 2. Nachträglich Eigenschaften hinzufügen

```js
person.beruf = "Entwickler";
person["stadt"] = "Berlin";
```

---

## 📖 Eigenschaften lesen

```js
console.log(person.vorname);     // Max
console.log(person["nachname"]); // Mustermann
```

---

## ✏️ Eigenschaften ändern

```js
person.alter = 31;
```

---

## ❌ Eigenschaften löschen

```js
delete person.istAktiv;
```

---

## ⚙️ Methoden – Funktionen im Objekt

```js
const auto = {
  marke: "BMW",
  starten: function() {
    console.log("Motor gestartet!");
  }
};

auto.starten(); // Motor gestartet!
```

💡 Modernere Schreibweise:

```js
const auto = {
  marke: "BMW",
  starten() {
    console.log("Motor gestartet!");
  }
};
```

---

## 🔁 Schleifen über Objekte

```js
for (let schlüssel in person) {
  console.log(`${schlüssel}: ${person[schlüssel]}`);
}
```

---

## 🧠 Das `this`-Schlüsselwort

```js
const benutzer = {
  name: "Anna",
  begruessung() {
    console.log(`Hallo, ich bin ${this.name}`);
  }
};

benutzer.begruessung(); // Hallo, ich bin Anna
```

**`this`** verweist **innerhalb eines Objekts** auf das Objekt selbst.

---

## 📦 Objekt in Objekt (verschachtelt)

```js
const firma = {
  name: "WebTech GmbH",
  adresse: {
    stadt: "München",
    plz: "80331"
  }
};

console.log(firma.adresse.stadt); // München
```

---

## 🛠 Nützliche Methoden

| Methode           | Beschreibung                                      |
|-------------------|---------------------------------------------------|
| `Object.keys(obj)`| Gibt alle Schlüssel als Array zurück              |
| `Object.values(obj)` | Gibt alle Werte zurück                        |
| `Object.entries(obj)`| Gibt `[key, value]` Paare zurück               |
| `Object.hasOwnProperty("key")` | Prüft, ob Eigenschaft existiert     |

---

## 🧪 Mini-Beispiel

```js
const buch = {
  titel: "JavaScript Basics",
  autor: "F. Fenzl",
  lesen() {
    return `Du liest gerade "${this.titel}" von ${this.autor}.`;
  }
};

console.log(buch.lesen());
// → Du liest gerade "JavaScript Basics" von F. Fenzl.
```

---

## 🧰 Objekte vs. Arrays

| Typ     | Beschreibung                            |
|---------|-----------------------------------------|
| Objekt  | Daten mit Namen (Schlüssel)             |
| Array   | Daten mit Position (Index)              |

```js
const person = { name: "Tom", alter: 25 };
const hobbies = ["Lesen", "Reisen", "Coden"];
```
