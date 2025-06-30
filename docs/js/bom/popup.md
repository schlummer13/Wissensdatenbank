# 💬 BOM – Popups & Dialoge (`alert`, `confirm`, `prompt`)

## 🧩 Was sind Browser-Popups?

JavaScript bietet dir drei einfache, eingebaute **Dialogfunktionen**, um mit dem Benutzer zu interagieren – ohne eigenes HTML:

| Methode     | Zweck                                | Interaktiv? |
|-------------|----------------------------------------|-------------|
| `alert()`   | Einfacher Hinweis                     | ❌ Nein     |
| `confirm()` | Ja/Nein-Abfrage                       | ✅ Ja       |
| `prompt()`  | Nutzereingabe                         | ✅ Ja       |

---

## ✅ `alert()` – Hinweis anzeigen

Zeigt eine einfache Nachricht mit einem OK-Button.

```js
alert("Hallo! Willkommen auf meiner Seite.");
```

🟡 Der Code pausiert, bis der Nutzer den Dialog schließt.

---

## ✅ `confirm()` – Bestätigung einholen

Fragt den Benutzer: "OK oder Abbrechen?" → gibt `true` oder `false` zurück.

```js
let istSicher = confirm("Möchtest du wirklich löschen?");
if (istSicher) {
  console.log("Wird gelöscht");
} else {
  console.log("Aktion abgebrochen");
}
```

---

## ✅ `prompt()` – Eingabe vom Nutzer

Zeigt ein Textfeld und gibt die Eingabe als String zurück.  
Bei Abbrechen: `null`.

```js
let name = prompt("Wie heißt du?");
console.log("Hallo " + name);
```

---

## 🧪 Beispiel: Kombination

```js
let name = prompt("Wie heißt du?");
if (name && confirm(`Bist du sicher, dass du ${name} heißt?`)) {
  alert(`Willkommen, ${name}!`);
} else {
  alert("Okay, kein Problem.");
}
```

---

## 🚫 Einschränkungen & Tipps

- Dialoge sind **synchron/blockierend** → kein schönes UX
- Modernes UI nutzt lieber **modale Fenster im HTML**
- Viele Browser blockieren **Popups automatisch**, wenn sie nicht durch direkte Benutzerinteraktion ausgelöst werden

---

## ✅ Zusammenfassung

| Methode   | Beschreibung                          | Rückgabe            |
|-----------|----------------------------------------|----------------------|
| `alert()` | Nur Hinweis                           | `undefined`          |
| `confirm()` | OK/Abbrechen                        | `true` oder `false`  |
| `prompt()` | Eingabe durch den Nutzer             | `string` oder `null` |
