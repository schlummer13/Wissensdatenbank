# `<script>` – Einbindung von JavaScript

## 🧩 Funktion

Das `<script>`-Tag wird in HTML verwendet, um **JavaScript-Code** in ein HTML-Dokument einzubetten oder zu verlinken.  
JavaScript ist eine **Client-seitige Skriptsprache**, mit der man Webseiten **interaktiv**, **dynamisch** und **reaktiv** gestalten kann.

---

## ✅ Grundverwendung

### 1. 📄 Internes Skript (direkt im HTML)

```html
<script>
  alert("Willkommen auf der Seite!");
</script>
```

👉 Führt den Code direkt beim Laden der Seite aus.

---

### 2. 🔗 Externes Skript (über Datei einbinden)

```html
<script src="main.js"></script>
```

👉 Bindet die Datei `main.js` ein. Vorteil: Wiederverwendbarkeit und saubere Trennung von Logik und Markup.

---

## 🔧 Wichtige Attribute von `<script>`

| Attribut     | Beschreibung |
|--------------|--------------|
| `src`        | Pfad zur externen JavaScript-Datei |
| `type`       | MIME-Type (meist `text/javascript`, aber optional) |
| `async`      | Führt das Skript **asynchron** aus – lädt parallel zum HTML |
| `defer`      | Führt das Skript **nach dem Parsen** des HTML-Dokuments aus |
| `crossorigin`| Für CORS (Cross-Origin Resource Sharing) |
| `nomodule`   | Skript wird **nicht geladen**, wenn der Browser Module (`type="module"`) unterstützt |
| `integrity`  | Prüft die Integrität des geladenen Skripts (Subresource Integrity) |
| `referrerpolicy` | Kontrolle über `Referer`-Header beim Laden des Skripts |

---

## 🚦 Platzierung im HTML

### Im `<head>`

```html
<head>
  <script src="head-script.js"></script>
</head>
```

🔴 Problem: Blockiert das Laden der Seite, wenn kein `defer` oder `async` verwendet wird.

### Vor `</body>`

```html
<body>
  ...
  <script src="script.js"></script>
</body>
```

🟢 Besser: Wird geladen, nachdem der HTML-Inhalt geparst wurde.

---

## ⚡ `defer` vs. `async`

| Attribut | Ausführung | Reihenfolge |
|----------|------------|-------------|
| `defer`  | Nach dem HTML-Parsing | In Dokument-Reihenfolge |
| `async`  | Sobald geladen | Reihenfolge **nicht garantiert** |

**Beispiel:**

```html
<script src="modulA.js" defer></script>
<script src="modulB.js" defer></script>
```

✅ `modulA` wird vor `modulB` ausgeführt – **Reihenfolge wird eingehalten**.

---

## 📦 `type="module"` (für moderne JavaScript-Module)

```html
<script type="module" src="app.js"></script>
```

➡ Ermöglicht das Verwenden von **ES6-Import/Export**, z. B.:

```js
// app.js
import { addiere } from './utils.js';
console.log(addiere(2, 3));
```

---

## 🔒 Sicherheit: Subresource Integrity (SRI)

```html
<script
  src="https://cdn.example.com/library.js"
  integrity="sha384-xyz123…"
  crossorigin="anonymous"
></script>
```

➡ Stellt sicher, dass das externe Skript nicht manipuliert wurde.

---

## 🧪 Beispiele

### 1. JavaScript im HTML

```html
<script>
  function begruessen(name) {
    alert("Hallo, " + name + "!");
  }
</script>

<button onclick="begruessen('Florian')">Sag Hallo</button>
```

### 2. Interaktive Einbindung (z. B. DOM-Manipulation)

```html
<script>
  document.addEventListener("DOMContentLoaded", function () {
    document.getElementById("demo").textContent = "Inhalt per JavaScript geändert!";
  });
</script>

<p id="demo">Ursprünglicher Inhalt</p>
```

---

## 🔍 Best Practices

- JavaScript-Dateien **modularisieren** und auslagern.
- **Nie `script`-Tags im `<head>` ohne `defer`** – sonst wird das Laden blockiert.
- **Kein inline-JS für große Funktionen** – Trennung von Struktur und Logik!
- Verwende `type="module"` für moderne, saubere Projekte.
- Nutze `defer` statt `async`, wenn die **Ausführungsreihenfolge** entscheidend ist.

---

## ♿ Barrierefreiheit & Performance

- Stelle sicher, dass deine Skripte **nicht essenzielle Inhalte ersetzen**, die nicht auch ohne JS verfügbar sind.
- JavaScript kann Inhalte dynamisch erzeugen – **achte auf Lesbarkeit für Screenreader**.
- Verwende `aria-`-Attribute oder `role`-Zuweisungen bei dynamischen DOM-Manipulationen.

---

## 📚 Fazit

Das `<script>`-Element ist der Schlüssel zur Interaktivität im Web. Egal ob du einfache Funktionen oder ganze Anwendungen umsetzt – korrekt eingesetzte Skripte machen Webseiten **lebendig, dynamisch und benutzerfreundlich**.
