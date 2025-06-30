# 🌐 BOM – Einführung

## 🧩 Was ist das BOM?

Das **BOM** (Browser Object Model) beschreibt alle **browserseitigen Funktionen**, die **außerhalb des DOM** existieren, aber trotzdem mit JavaScript genutzt werden können.  
Es erlaubt dir, direkt mit dem **Browser-Fenster**, dem **Verlauf**, der **Adresse**, dem **Bildschirm**, den **Cookies**, dem **Speicher** und vielem mehr zu interagieren.

👉 Während das **DOM** für den Inhalt zuständig ist, ermöglicht das **BOM die Interaktion mit dem Browser selbst**.

---

## 📦 BOM vs DOM

| DOM                             | BOM                                  |
|----------------------------------|--------------------------------------|
| Manipuliert HTML & CSS           | Steuert Browserfunktionen            |
| Zugriff auf Seiteninhalte        | Zugriff auf Fenster, URL, Tabs etc.  |
| `document`                       | `window`, `location`, `navigator` etc.|

---

## 📚 Wichtige BOM-Komponenten

| Objekt         | Beschreibung                                      |
|----------------|---------------------------------------------------|
| `window`       | Das Browserfenster selbst – Wurzel aller BOM-Objekte |
| `screen`       | Informationen über den Bildschirm (Größe, Auflösung) |
| `location`     | Aktuelle URL & Weiterleitungen                    |
| `history`      | Browser-Verlauf (vor/zurück navigieren)           |
| `navigator`    | Infos über den Browser & das Gerät                |
| `alert` / `confirm` / `prompt` | Einfache Dialogboxen                  |
| `setTimeout`, `setInterval` | Zeitgesteuerte Funktionen             |
| `localStorage`, `sessionStorage` | Lokaler Webspeicher im Browser    |
| `cookies`      | Informationen speichern (z. B. Nutzerzustimmung)  |
| `geolocation`  | Aktuellen Standort ermitteln                      |

---

## ✅ Warum ist das BOM wichtig?

- Ermöglicht **Browser-Steuerung** aus JavaScript heraus
- Unverzichtbar für **moderne Web-Apps**
- Grundlage für **Sicherheit, Lokalisierung, Nutzererfahrung**
- Wird von **jedem Browser** unterstützt

---

## 🔗 Beispiele für BOM-Einsätze

- URL umleiten: `location.href = "https://example.com"`
- Fenster öffnen: `window.open()`
- Popups blockieren: `alert("Achtung!")`
- Lokale Daten speichern: `localStorage.setItem("name", "Florian")`
- Position abfragen: `navigator.geolocation.getCurrentPosition(...)`
- Zurück navigieren: `history.back()`

---

## 🧠 Merksatz

> **BOM = JavaScript + Browsersteuerung**

Ohne BOM könnten Webseiten keine Tabs öffnen, keine URL ändern, keine Infos über den User sammeln oder sich merken, was im letzten Besuch passiert ist.
