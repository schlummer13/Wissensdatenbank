# 🧾 DOM – Formulare

## 🧩 Was macht das DOM mit Formularen?

Mit dem DOM kannst du:

- Formularfelder **auslesen**
- Eingaben **prüfen (validieren)**
- Werte **setzen oder zurücksetzen**
- Formularaktionen **abfangen**, bevor sie an den Server gesendet werden

---

## 📌 Zugriff auf Formulare und Felder

```html
<form id="kontaktForm">
  <input type="text" name="name" />
  <input type="email" name="email" />
  <button type="submit">Absenden</button>
</form>
```

```js
const form = document.getElementById("kontaktForm");
const nameFeld = form.elements["name"];
const emailFeld = form.elements["email"];

console.log(nameFeld.value); // Eingabe lesen
```

---

## ✍️ Werte setzen

```js
nameFeld.value = "Max Mustermann";
emailFeld.value = "max@example.com";
```

---

## ✅ Eingaben prüfen (Validation)

```js
form.addEventListener("submit", function (event) {
  if (nameFeld.value === "") {
    alert("Name darf nicht leer sein!");
    event.preventDefault(); // Verhindert das Absenden
  }
});
```

---

## 🔁 Formular zurücksetzen

```js
form.reset(); // Alle Felder auf Ausgangswerte setzen
```

---

## 🧠 Zugriff auf `.elements`

Jedes `<form>`-Element hat eine `elements`-Eigenschaft, mit der du direkt auf die Felder zugreifen kannst:

```js
form.elements["email"].value;
```

---

## 🛠 Einzelne Typen gezielt ansprechen

```js
const checkbox = document.querySelector('input[type="checkbox"]');
if (checkbox.checked) {
  console.log("Checkbox ist angehakt");
}
```

---

## 🧪 Dynamisches Formularverhalten

```js
emailFeld.addEventListener("input", () => {
  console.log("Der Nutzer tippt: " + emailFeld.value);
});
```

---

## 💡 Best Practice: Event-Delegation für Buttons

```js
form.addEventListener("submit", (e) => {
  e.preventDefault();
  // Verarbeitung der Eingaben hier
});
```

---

## 📑 Beispiel: Einfaches Login-Formular

```html
<form id="loginForm">
  <input type="text" name="user" placeholder="Benutzername" />
  <input type="password" name="passwort" />
  <button type="submit">Einloggen</button>
</form>
```

```js
document.getElementById("loginForm").addEventListener("submit", function (e) {
  e.preventDefault();
  const user = this.elements["user"].value;
  const pw = this.elements["passwort"].value;

  if (user && pw) {
    alert("Login wird verarbeitet...");
  } else {
    alert("Bitte alle Felder ausfüllen!");
  }
});
```

---

## ✅ Zusammenfassung

| Aktion                  | Methode/Eigenschaft           |
|--------------------------|------------------------------|
| Formular holen           | `getElementById("...")`      |
| Felder auslesen          | `form.elements["name"].value`|
| Werte setzen             | `.value = "..."`             |
| Validieren               | `if (feld.value === "")`     |
| Absenden abfangen        | `event.preventDefault()`     |
| Zurücksetzen             | `form.reset()`               |
