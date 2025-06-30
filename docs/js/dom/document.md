# 📄 JavaScript DOM – `document`-Objekt

## 🧩 Was ist `document`?

`document` ist das **zentralste Objekt** im DOM. Es stellt deine **gesamte HTML-Seite als JavaScript-Objekt** dar.

> Es ist der **Einstiegspunkt**, um auf alle HTML-Elemente, Inhalte und Strukturen zuzugreifen und sie zu verändern.

---

## 📦 Beispiele für Zugriffe

```js
console.log(document.title);      // Titel der Seite
console.log(document.body);       // Gibt den <body> zurück
console.log(document.URL);        // Aktuelle Seiten-URL
console.log(document.documentElement); // <html>-Element
```

---

## 🔍 Zugriff auf Elemente

| Methode                       | Zweck                                  |
|-------------------------------|-----------------------------------------|
| `getElementById()`            | Zugriff per ID                         |
| `getElementsByClassName()`    | Zugriff auf Klassen                    |
| `getElementsByTagName()`      | Zugriff auf Tag-Namen                  |
| `querySelector()`             | CSS-Selektor, erstes passendes Element |
| `querySelectorAll()`          | CSS-Selektor, alle passenden Elemente  |

```js
document.getElementById("main");
document.querySelector(".btn");
```

---

## 🛠️ Seiteneigenschaften

| Eigenschaft               | Bedeutung                            |
|---------------------------|---------------------------------------|
| `document.title`          | Titel der Seite                      |
| `document.URL`            | Aktuelle URL                         |
| `document.domain`         | Domain der Seite                     |
| `document.referrer`       | Seite, von der der Nutzer kam        |
| `document.cookie`         | Zugriff auf Cookies                  |
| `document.lastModified`   | Letztes Änderungsdatum               |

---

## ✏️ Seiteneigenschaften ändern

```js
document.title = "Neuer Seitentitel";
```

---

## 🧱 Neue Elemente erstellen

```js
const neu = document.createElement("p");
neu.textContent = "Hallo, ich bin neu!";
document.body.appendChild(neu);
```

---

## 📑 Zugriff auf spezielle Bereiche

| Bereich             | Beschreibung                     |
|---------------------|----------------------------------|
| `document.head`     | `<head>`-Element                 |
| `document.body`     | `<body>`-Element                 |
| `document.forms`    | Alle Formulare als Sammlung      |
| `document.images`   | Alle Bilder auf der Seite        |
| `document.links`    | Alle `<a>`-Tags mit `href`       |

---

## 📐 Seitenweite Struktur

```js
document.documentElement // <html>
document.head            // <head>
document.body            // <body>
```

---

## 📣 Events im `document`

Du kannst auf Events der ganzen Seite hören:

```js
document.addEventListener("DOMContentLoaded", () => {
  console.log("Seite ist vollständig geladen (ohne Bilder)");
});
```

---

## 🔒 Schreibschutz (Read-only vs. beschreibbar)

Einige Eigenschaften sind nur lesbar:

```js
console.log(document.URL);        // Nur lesbar
console.log(document.lastModified); // Nur lesbar
```

---

## ✅ Zusammenfassung

| Was du brauchst              | Nutze dies                        |
|------------------------------|-----------------------------------|
| Zugriff auf Elemente         | `querySelector`, `getElementById` |
| Seiteneigenschaften lesen    | `document.title`, `document.URL` |
| HTML-Struktur bearbeiten     | `createElement`, `appendChild`   |
| Bereich gezielt ansprechen   | `document.head`, `.body`, `.forms` |
| Events der Seite verwalten   | `DOMContentLoaded`, etc.         |

