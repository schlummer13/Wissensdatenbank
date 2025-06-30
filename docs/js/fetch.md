# 🌐 `fetch()` für HTTP-Anfragen

Mit `fetch()` kannst du in JavaScript **Daten von Servern laden oder senden** – z. B. JSON von einer API abrufen, Formulare verschicken oder Dateien hochladen.

> `fetch()` ist modern, basiert auf **Promises** und ersetzt ältere Techniken wie `XMLHttpRequest`.

---

## 📦 Syntax – Grundstruktur

```js
fetch("https://api.example.com/daten")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error("Fehler:", error));
```

### Erklärung:
- `fetch(URL)` – startet eine HTTP-Anfrage
- `.then()` – wartet auf Antwort (Promise)
- `.json()` – wandelt Antwort in echtes JS-Objekt um
- `.catch()` – fängt Fehler ab

---

## ✅ GET-Anfrage (Daten abrufen)

```js
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then(res => res.json())
  .then(data => {
    console.log("Titel:", data.title);
  });
```

---

## ✉️ POST-Anfrage (Daten senden)

```js
fetch("https://jsonplaceholder.typicode.com/posts", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    title: "Hallo Welt",
    body: "Das ist ein Beispiel",
    userId: 1
  })
})
  .then(res => res.json())
  .then(data => console.log(data));
```

---

## 🧠 Weitere HTTP-Methoden

| Methode | Zweck                          |
|---------|--------------------------------|
| `GET`   | Daten abrufen (Standard)       |
| `POST`  | Neue Daten senden              |
| `PUT`   | Vorhandene Daten überschreiben |
| `PATCH` | Teilweise aktualisieren        |
| `DELETE` | Daten löschen                 |

---

## 🔧 Optionen-Objekt

```js
fetch(url, {
  method: "POST",         // GET, POST, PUT, DELETE, ...
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify(daten) // nur bei POST, PUT, PATCH
});
```

---

## ❗ Fehlerbehandlung

```js
fetch("/api/info")
  .then(res => {
    if (!res.ok) {
      throw new Error(`HTTP-Fehler: ${res.status}`);
    }
    return res.json();
  })
  .then(data => console.log(data))
  .catch(err => console.error("Fehler:", err.message));
```

---

## 🔄 Asynchrone Schreibweise mit `async/await`

```js
async function ladeDaten() {
  try {
    const res = await fetch("https://api.example.com");
    if (!res.ok) throw new Error("Fehler beim Laden");
    const data = await res.json();
    console.log(data);
  } catch (e) {
    console.error("Fehler:", e.message);
  }
}

ladeDaten();
```

---

## 📤 Formulardaten mit `FormData`

```js
const form = document.querySelector("form");
const daten = new FormData(form);

fetch("/kontakt", {
  method: "POST",
  body: daten
});
```

> `FormData` sendet alle Felder automatisch im richtigen Format!

---

## 🔐 Mit Authentifizierung (z. B. Bearer Token)

```js
fetch("https://api.example.com/user", {
  headers: {
    "Authorization": "Bearer DEIN_TOKEN"
  }
})
  .then(res => res.json())
  .then(data => console.log(data));
```

---

## 🧪 Beispiel: Benutzer aus API laden

```js
async function holeBenutzer(id) {
  const res = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);
  const user = await res.json();
  console.log(`Name: ${user.name}, Email: ${user.email}`);
}

holeBenutzer(3);
```

---

## ✅ Zusammenfassung

| Was?                 | Wie?                                         |
|----------------------|----------------------------------------------|
| Daten abrufen        | `fetch(url)`                                 |
| Daten senden         | `method: "POST"`, `body`, `headers`          |
| JSON verarbeiten     | `res.json()`                                 |
| Fehler abfangen      | `if (!res.ok) throw Error()` + `catch()`     |
| Einfach schreiben    | mit `async/await`                            |
| Form senden          | `FormData` verwenden                         |
| Auth verwenden       | `Authorization`-Header setzen                |

