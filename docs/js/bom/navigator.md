# 🧭 BOM – `navigator`

## 🧩 Was ist das `navigator`-Objekt?

Das `navigator`-Objekt liefert **Informationen über den Browser und das Gerät**, auf dem die Webseite angezeigt wird.  
Dazu gehören z. B. **Browsername**, **Sprache**, **Online-Status**, **Betriebssystem** oder **Unterstützung für Funktionen** wie `geolocation`.

> 📌 Das `navigator`-Objekt ist **read-only**, d. h. du kannst es nur **auslesen**, aber nicht verändern.

---

## ✅ Zugriff

```js
console.log(navigator);
```

---

## 📚 Häufig genutzte Eigenschaften

| Eigenschaft            | Beschreibung                                      |
|------------------------|---------------------------------------------------|
| `userAgent`            | String mit Infos über Browser und Betriebssystem |
| `language`             | Vom Nutzer eingestellte Sprache (`de`, `en-US`)  |
| `languages`            | Sprachpräferenzen als Array                      |
| `platform`             | Betriebssystem (`Win32`, `Linux x86_64`, …)     |
| `onLine`               | `true` oder `false` → Netzwerkverbindung         |
| `cookieEnabled`        | Gibt an, ob Cookies erlaubt sind                 |
| `hardwareConcurrency`  | Anzahl logischer Prozessoren                     |
| `deviceMemory`         | Arbeitsspeicher in GB (z. B. `8`)                |
| `webdriver`            | `true`, wenn über Automation (z. B. Selenium)    |

---

## 🧪 Beispiel: Nutzerinformationen anzeigen

```js
console.log("Sprache:", navigator.language);
console.log("System:", navigator.platform);
console.log("Online:", navigator.onLine);
```

---

## 📍 Geolocation (siehe eigenes Kapitel)

```js
if ("geolocation" in navigator) {
  navigator.geolocation.getCurrentPosition((position) => {
    console.log(position.coords.latitude, position.coords.longitude);
  });
}
```

---

## 🧠 Warum ist `navigator` wichtig?

- Um **Gerätebedingungen** zu erkennen (z. B. RAM, CPU, Sprache)
- Für **Fehlermeldungen und Unterstützung** („Browser nicht unterstützt“)
- Um zu sehen, ob ein Benutzer **online oder offline** ist
- Für **Progressive Web Apps** oder Feature Detection

---

## 🔐 Datenschutz-Hinweis

`navigator.userAgent` kann zur **Browser-Fingerabdruck-Erkennung** genutzt werden.  
Moderne Browser limitieren deshalb manche Infos gezielt.

---

## ✅ Zusammenfassung

| Zweck                          | Eigenschaft / Methode      |
|--------------------------------|-----------------------------|
| Sprache erkennen               | `navigator.language`        |
| System erkennen                | `navigator.platform`        |
| Browserinfo anzeigen           | `navigator.userAgent`       |
| Ist Nutzer online?            | `navigator.onLine`          |
| Cookies erlaubt?              | `navigator.cookieEnabled`   |
| RAM & CPU erkennen (evtl.)    | `navigator.deviceMemory`, `hardwareConcurrency` |
| Geolocation möglich?          | `"geolocation" in navigator` |

