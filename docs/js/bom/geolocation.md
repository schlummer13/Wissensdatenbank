# 📍 BOM – Geolocation

## 🧩 Was ist Geolocation?

Die **Geolocation API** erlaubt es dir, den **aktuellen geografischen Standort des Nutzers** zu ermitteln – z. B. für Karten, Wetterdaten, Navigation oder standortbasierte Dienste.

> ✅ Funktioniert nur, wenn der Nutzer **zustimmt** (z. B. über einen Browser-Dialog).

---

## ✅ Prüfung auf Unterstützung

```js
if ("geolocation" in navigator) {
  console.log("Geolocation wird unterstützt!");
} else {
  console.log("Geolocation ist nicht verfügbar.");
}
```

---

## 🗺️ Standort abrufen – `getCurrentPosition()`

```js
navigator.geolocation.getCurrentPosition(
  (position) => {
    console.log("Latitude:", position.coords.latitude);
    console.log("Longitude:", position.coords.longitude);
  },
  (error) => {
    console.warn("Fehler:", error.message);
  }
);
```

### 🔧 Rückgabe-Objekt: `position.coords`

| Eigenschaft         | Beschreibung                   |
|----------------------|--------------------------------|
| `latitude`           | Breitengrad                   |
| `longitude`          | Längengrad                    |
| `accuracy`           | Genauigkeit in Metern         |
| `altitude`           | Höhe (nicht immer verfügbar)  |
| `speed`              | Geschwindigkeit               |
| `heading`            | Bewegungsrichtung             |

---

## 📡 Optionen mit `getCurrentPosition()`

```js
const options = {
  enableHighAccuracy: true,
  timeout: 5000,
  maximumAge: 0,
};

navigator.geolocation.getCurrentPosition(success, error, options);
```

| Option               | Beschreibung                                      |
|----------------------|---------------------------------------------------|
| `enableHighAccuracy` | GPS nutzen (langsamer, aber genauer)              |
| `timeout`            | Abbruchzeit in ms                                 |
| `maximumAge`         | Alter der zwischengespeicherten Position (ms)     |

---

## 🔄 Live-Tracking mit `watchPosition()`

```js
const watcher = navigator.geolocation.watchPosition(
  (position) => {
    console.log("Neue Position:", position.coords.latitude, position.coords.longitude);
  }
);
```

### 🛑 Stoppen mit `clearWatch()`

```js
navigator.geolocation.clearWatch(watcher);
```

---

## 🧠 Sicherheit & Datenschutz

- Funktioniert **nur über HTTPS** (außer `localhost`)
- Nutzer müssen **aktiv zustimmen**
- Daten können je nach Gerät/GPS sehr unterschiedlich genau sein
- Du solltest **eine Fallback-Funktion** anbieten

---

## ✅ Zusammenfassung

| Ziel                              | Methode                            |
|-----------------------------------|-------------------------------------|
| Einmaliger Standort               | `getCurrentPosition()`              |
| Kontinuierliches Tracking         | `watchPosition()`                   |
| Stoppen des Trackings             | `clearWatch(id)`                    |
| Genauigkeit erhöhen               | `enableHighAccuracy: true`          |
| Fehlerbehandlung                  | Fehler-Callback im zweiten Argument |

---

## 🧪 Beispiel: Karte mit Koordinaten

```js
navigator.geolocation.getCurrentPosition((pos) => {
  const { latitude, longitude } = pos.coords;
  window.location.href = `https://www.google.com/maps?q=${latitude},${longitude}`;
});
```
