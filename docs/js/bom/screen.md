# 🖥️ BOM – `screen`-Objekt

## 🧩 Was ist das `screen`-Objekt?

Das `screen`-Objekt liefert **Informationen über den physischen Bildschirm**, auf dem sich das Browserfenster befindet.  
Es ist hilfreich für **responsive Designs**, **Popup-Positionierung**, **Bildschirmanalysen** und mehr.

> Hinweis: `screen` beschreibt **den Monitor**, nicht den Viewport (→ das übernimmt `window.innerWidth`).

---

## ✅ Beispiel

```js
console.log(screen);
```

Gibt das komplette `screen`-Objekt mit seinen Eigenschaften aus.

---

## 🧠 Nützliche Eigenschaften

| Eigenschaft             | Beschreibung                                |
|--------------------------|---------------------------------------------|
| `screen.width`          | Gesamte Bildschirmbreite in Pixeln           |
| `screen.height`         | Gesamte Bildschirmhöhe in Pixeln            |
| `screen.availWidth`     | Verfügbare Breite ohne Taskleisten etc.     |
| `screen.availHeight`    | Verfügbare Höhe ohne z. B. Taskleiste        |
| `screen.colorDepth`     | Farbtiefe in Bit (z. B. 24 oder 32)          |
| `screen.pixelDepth`     | Pixeltiefe pro Farbe (meist gleich `colorDepth`) |

---

## 🔍 Unterschied zu `window`

| Objekt    | Was es misst                   |
|-----------|--------------------------------|
| `screen`  | Physische Größe des Monitors   |
| `window`  | Aktueller sichtbarer Bereich   |

---

## 🧪 Beispiel: Bildschirmgröße anzeigen

```js
console.log(`Bildschirmgröße: ${screen.width} × ${screen.height}`);
console.log(`Verfügbar: ${screen.availWidth} × ${screen.availHeight}`);
```

---

## 📌 Praktische Anwendungsfälle

- Center-Positionierung von Popups:
  ```js
  const left = (screen.availWidth - 600) / 2;
  const top = (screen.availHeight - 400) / 2;

  window.open("popup.html", "Popup", `width=600,height=400,left=${left},top=${top}`);
  ```

- Erkennung von ungewöhnlich kleinen Bildschirmen (z. B. für mobile Layouts)

---

## 🚫 Einschränkungen

- Aus Datenschutzgründen oft **nicht 100 % exakt** in mobilen Browsern
- Kein Zugriff auf mehrere Monitore (nur Hauptscreen)

---

## ✅ Zusammenfassung

| Punkt               | Bedeutung                                  |
|---------------------|---------------------------------------------|
| Info über Monitor   | Nicht Viewport, sondern physischer Bildschirm |
| Nutzt man selten    | Aber hilfreich für besondere Layouts/Popups  |
| Schnell verfügbar   | Kein zusätzlicher Zugriff notwendig          |
