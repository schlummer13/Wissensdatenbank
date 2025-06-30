# 🏷️ Object Properties (Eigenschaften)

**Eigenschaften** sind die Bausteine von Objekten in JavaScript. Sie bestehen aus **Schlüssel-Wert-Paaren** (Key-Value). Mit ihnen speicherst und strukturierst du beliebige Daten in einem Objekt.

---

## 🧱 Eigenschaften erstellen

### 🔹 Beim Erstellen eines Objekts

```js
const person = {
  name: "Florian",
  alter: 33,
  beruf: "Entwickler"
};
```

---

## 🔍 Eigenschaften lesen

```js
console.log(person.name);      // Florian
console.log(person["alter"]);  // 33
```

> Mit Punktnotation (`.`) oder Klammernotation (`[""]`)

---

## ✏️ Eigenschaften ändern

```js
person.alter = 34;
person["beruf"] = "Data Scientist";
```

---

## ➕ Neue Eigenschaft hinzufügen

```js
person.hobby = "Coden";
```

---

## ❌ Eigenschaft löschen

```js
delete person.beruf;
```

---

## 📦 Dynamische Schlüssel

```js
let eigenschaft = "wohnort";
person[eigenschaft] = "München";
```

---

## ✅ Prüfen ob Eigenschaft existiert

```js
"alter" in person         // true
person.hasOwnProperty("name") // true
```

---

## 🔁 Über Eigenschaften iterieren

```js
for (let key in person) {
  console.log(key, person[key]);
}
```

---

## 🧠 Property Descriptors (erweitert)

Jede Eigenschaft hat **interne Einstellungen**:

| Descriptor  | Bedeutung                                     |
|-------------|------------------------------------------------|
| `value`     | Der gespeicherte Wert                         |
| `writable`  | Ob der Wert geändert werden kann              |
| `enumerable`| Ob die Eigenschaft durch `for...in` erscheint |
| `configurable` | Ob sie gelöscht oder verändert werden kann |

Beispiel:

```js
Object.defineProperty(person, "id", {
  value: 123,
  writable: false,
  enumerable: true,
  configurable: false
});
```

---

## 📋 Eigenschaften auflisten

```js
Object.keys(person);     // ["name", "alter", "hobby"]
Object.values(person);   // ["Florian", 34, "Coden"]
Object.entries(person);  // [["name", "Florian"], ["alter", 34], ...]
```

---

## 🔧 Kurzschreibweise (ab ES6)

```js
let vorname = "Max";
let nutzer = { vorname };  // { vorname: "Max" }
```

---

## 🔁 Spread & Shallow Copy

```js
let kopie = { ...person }; // flache Kopie
```

---

## 📚 Eigenschaften auslesen (Destructuring)

```js
const { name, alter } = person;
console.log(name); // Florian
```

---

## 🔐 Getter & Setter

```js
const user = {
  vorname: "Anna",
  nachname: "Schmidt",
  
  get vollerName() {
    return `${this.vorname} ${this.nachname}`;
  },

  set vollerName(name) {
    [this.vorname, this.nachname] = name.split(" ");
  }
};

console.log(user.vollerName); // Anna Schmidt
user.vollerName = "Lisa Meier";
console.log(user.vorname);    // Lisa
```

---

## 🗂 Datei-Vorschlag: `javascript/object-properties.md`

---

## ✅ Zusammenfassung

| Aktion             | Beispiel                                |
|--------------------|------------------------------------------|
| Lesen              | `obj.key` oder `obj["key"]`             |
| Schreiben          | `obj.key = wert`                        |
| Hinzufügen         | `obj.neu = wert`                        |
| Löschen            | `delete obj.key`                        |
| Prüfen             | `"key" in obj` / `obj.hasOwnProperty()` |

