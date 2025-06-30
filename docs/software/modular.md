# 🧩 Modularität in der Softwareentwicklung

**Modularität** bedeutet, ein Programm in **kleine, unabhängige und wiederverwendbare Bausteine** zu zerlegen. Jeder dieser **Module** erfüllt eine **klar definierte Aufgabe**.

Dieses Prinzip hilft dabei, **komplexe Software verständlich, testbar und wartbar** zu halten.

---

## 🎯 Warum modular entwickeln?

| Vorteil                  | Erklärung                                               |
|--------------------------|----------------------------------------------------------|
| 🔁 Wiederverwendbarkeit  | Ein Modul kann in mehreren Projekten oder Bereichen genutzt werden |
| 🧪 Testbarkeit           | Kleine Module lassen sich leichter einzeln testen       |
| 🔧 Wartbarkeit           | Änderungen an einem Modul beeinflussen andere nicht      |
| 👥 Teamarbeit            | Mehrere Entwickler können unabhängig an einzelnen Modulen arbeiten |
| 📦 Austauschbarkeit      | Module lassen sich leichter durch bessere Varianten ersetzen |

---

## 🧠 Was ist ein Modul?

Ein **Modul** ist eine **Einheit von Code**, z. B.:

- Eine Datei in JavaScript/Python
- Eine Klasse oder Funktion
- Ein wiederverwendbarer Baustein wie ein Button oder ein Formular

**Beispiel (JavaScript ES6):**

```js
// datei: mathe.js
export function addiere(a, b) {
  return a + b;
}
```

```js
// datei: app.js
import { addiere } from "./mathe.js";
console.log(addiere(2, 3)); // 5
```

➡️ Die Funktion `addiere` ist **modularisiert**.

---

## 🔧 So baust du modularen Code

### ✅ 1. **Ein Modul = eine Aufgabe**

Beispiel: Statt `utils.js` mit 100 Funktionen → lieber:

- `rechnung.js` → enthält Rechenfunktionen
- `benutzer.js` → verwaltet Benutzerlogik
- `validierung.js` → enthält Prüfungen für Formulare

---

### ✅ 2. **Explizite Schnittstellen (APIs)**

Ein Modul sollte **nur das nach außen geben**, was andere brauchen.

```js
// Nur bestimmte Funktionen exportieren
export function berechneMwst() { ... }
export function berechneRabatt() { ... }
// interne Hilfsfunktion bleibt privat
function loggeZahl() { ... }
```

---

### ✅ 3. **Keine globalen Variablen!**

Jedes Modul sollte seinen eigenen **Scope** haben und **keine globale Umwelt verändern**.

---

### ✅ 4. **Unabhängigkeit**

Module sollten **nicht gegenseitig abhängig** sein. Verwende **Entkopplung**:

- **Callbacks**
- **Events**
- **Dependency Injection**

---

## 📦 Modulsysteme in verschiedenen Sprachen

| Sprache     | Modulsystem                    |
|-------------|--------------------------------|
| JavaScript  | CommonJS (Node.js), ES Modules |
| Python      | Module (Dateien mit Funktionen/Klassen) |
| Java        | Packages                       |
| PHP         | `require`, `include`, Namespaces |
| C#          | Namespaces & Assemblies        |

---

## 🔁 Beispiel in Python

```python
# datei: tools.py
def begruessen(name):
    return f"Hallo, {name}!"

# datei: app.py
from tools import begruessen

print(begruessen("Florian"))
```

---

## 🧠 Best Practices für Modularität

| Regel                            | Warum?                              |
|----------------------------------|--------------------------------------|
| Schreibe kleine, fokussierte Module | Klarer Zweck – bessere Wiederverwendung |
| Verwende sprechende Dateinamen     | `mathUtils.js` statt `script1.js`   |
| Nur exportieren, was nötig ist     | Weniger Kopplung, mehr Kontrolle    |
| Nutze Ordner für Gruppierungen     | z. B. `components/`, `services/`, `utils/` |
| Teste Module **isoliert**          | Schnellere Fehlersuche              |

---

## 🧱 Modularität in der Praxis (Beispiel mit Frontend-Komponenten)

Struktur für z. B. eine React/Vue/JS-Web-App:

```
/components
  ├── Button.js
  ├── Input.js
  └── Modal.js

/utils
  └── formatDate.js

/services
  └── api.js
```

➡️ Jedes Modul hat **nur einen Zweck**  
➡️ Wird bei Bedarf importiert

---

## 📘 Fazit

> **Modularer Code ist wie ein LEGO-Baukasten:**
> Du kannst komplexe Dinge bauen – aber alles bleibt verständlich, testbar und austauschbar.

- Besser **5 kleine Dateien** als 1 große
- Jedes Modul sollte **getestet**, **lesbar** und **unabhängig** sein
- Modularität ist der **Schlüssel zu skalierbarer Softwareentwicklung**