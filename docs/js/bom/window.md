# 🪟 BOM – `window`-Objekt

## 🧩 Was ist das `window`-Objekt?

Das `window`-Objekt ist das **globale Hauptobjekt** im Browser.  
Es **repräsentiert das aktuelle Browserfenster oder den Tab** – und ist das zentrale Element des Browser Object Models (BOM).

👉 In einer Browserumgebung ist **alles global Verfügbare eine Eigenschaft von `window`**.

---

## ✅ Beispiel

```js
console.log(window); // Gibt das komplette Fensterobjekt aus
```

> Hinweis: Wenn du z. B. `alert()`, `document`, `setTimeout()` schreibst, ist das eigentlich:
>
> `window.alert()`, `window.document`, `window.setTimeout()` usw.

---

## 📚 Nützliche Eigenschaften & Methoden

| Eigenschaft / Methode     | Beschreibung                                |
|---------------------------|---------------------------------------------|
| `window.innerWidth`       | Innere Breite des Fensters (Viewport)       |
| `window.innerHeight`      | Innere Höhe des Fensters (Viewport)         |
| `window.outerWidth`       | Gesamte Fensterbreite inkl. Ränder etc.     |
| `window.outerHeight`      | Gesamte Fensterhöhe inkl. Ränder etc.       |
| `window.screenX` / `Y`    | Fensterposition relativ zum Bildschirm       |
| `window.scrollX` / `Y`    | Aktueller Scroll-Wert (horizontal/vertikal) |
| `window.location`         | URL-Objekt (siehe eigenes Kapitel)          |
| `window.document`         | Das DOM (siehe DOM-Themenreihe)             |
| `window.alert()`          | Dialogfenster (siehe "Popup Alert")         |
| `window.setTimeout()`     | Zeitgesteuerte Funktion (siehe "Timing")    |
| `window.open()`           | Neues Browserfenster/Tabs                   |

---

## 🧠 Globale Variablen sind Teil von `window`

```js
let name = "Florian";
console.log(window.name); // "Florian"
```

> Das gilt nur für `var` oder nicht deklarierte Variablen – **nicht** bei `let`/`const` im strict mode.

---

## 🔐 Sicherheit & Zugriff

- Einige Funktionen wie `window.open()` oder `window.close()` werden aus **Sicherheitsgründen vom Browser eingeschränkt** (z. B. Popup-Blocker).
- Globale Fensterkommunikation ist möglich über `window.postMessage()` (Cross-Origin-Kommunikation).

---

## 🛠 Beispiel: Fenstermaße ermitteln

```js
console.log(`Breite: ${window.innerWidth}px`);
console.log(`Höhe: ${window.innerHeight}px`);
```

---

## 📌 Hinweis

Wenn du JavaScript im Browser verwendest, kannst du `window` meist **weglassen**, weil es der globale Kontext ist.

```js
alert("Hallo"); // entspricht window.alert("Hallo")
```

---

## ✅ Zusammenfassung

| Punkt                 | Bedeutung                                  |
|-----------------------|---------------------------------------------|
| Globales Objekt       | Alles läuft über `window` im Browser        |
| Zugriff auf Browser   | Größe, Position, Tabs, Timing, Location etc. |
| BOM-Wurzel            | Elternobjekt für alle BOM-Komponenten       |
