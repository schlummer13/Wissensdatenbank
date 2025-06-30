# 🧬 MutationObserver

## 🧩 Was ist ein MutationObserver?

Ein **MutationObserver** ist eine JavaScript-API, mit der du **Änderungen am DOM automatisch erkennen** kannst – z. B. wenn:

- ein neues Element eingefügt wird,
- sich Text verändert,
- Attribute geändert werden,
- oder ganze Knoten gelöscht werden.

👉 Ideal für dynamische UIs, Frameworks oder Monitoring-Funktionen!

---

## 🧠 Warum nicht einfach Event Listener?

Event Listener beobachten **Benutzeraktionen** (z. B. Klick, Scroll).  
**MutationObserver** beobachtet **DOM-Veränderungen im Hintergrund** – ohne, dass der Nutzer aktiv etwas macht.

---

## 🛠️ Syntax

```js
const observer = new MutationObserver(callback);
observer.observe(zielElement, optionen);
```

| Teil          | Bedeutung                                            |
|---------------|-------------------------------------------------------|
| `callback`    | Funktion, die bei Änderung aufgerufen wird           |
| `zielElement` | DOM-Element, das beobachtet wird                     |
| `optionen`    | Welche Arten von Änderungen sollen erkannt werden?   |

---

## ✅ Einfaches Beispiel

```js
const ziel = document.getElementById("inhalt");

const observer = new MutationObserver((mutationen) => {
  console.log("Mutation erkannt:", mutationen);
});

observer.observe(ziel, {
  childList: true,
  subtree: true
});
```

📌 Beobachtet, ob innerhalb von `#inhalt` Knoten hinzugefügt oder entfernt werden.

---

## ⚙️ Optionen im Detail

| Option           | Beschreibung                                      |
|------------------|---------------------------------------------------|
| `childList`      | neue/gelöschte Kindknoten                         |
| `attributes`     | Änderungen an Attributen erkennen                 |
| `subtree`        | gesamte Nachkommen-Struktur überwachen           |
| `characterData`  | Textänderungen beobachten                         |
| `attributeFilter`| Nur bestimmte Attribute beobachten                |
| `attributeOldValue` | Vorheriger Attributwert speichern             |
| `characterDataOldValue` | Vorheriger Textwert speichern             |

---

## 🧪 Beispiel: Textänderungen beobachten

```js
const p = document.querySelector("p");

const observer = new MutationObserver((mutations) => {
  mutations.forEach(m => {
    console.log("Alter Text:", m.oldValue);
    console.log("Neuer Text:", m.target.textContent);
  });
});

observer.observe(p, {
  characterData: true,
  subtree: true,
  characterDataOldValue: true
});
```

---

## 🧹 Beobachtung beenden

```js
observer.disconnect();
```

Beendet das Beobachten. Wichtig, um Performance zu optimieren!

---

## 📦 Komplexes Beispiel: Attribut & Struktur

```js
const target = document.querySelector("#element");

const observer = new MutationObserver((mutationList) => {
  for (let mutation of mutationList) {
    if (mutation.type === "attributes") {
      console.log("Attribut geändert:", mutation.attributeName);
    }
    if (mutation.type === "childList") {
      console.log("Knoten hinzugefügt/entfernt");
    }
  }
});

observer.observe(target, {
  attributes: true,
  childList: true,
  subtree: true
});
```

---

## ✅ Zusammenfassung

| Vorteil                       | Beschreibung                                 |
|------------------------------|----------------------------------------------|
| Automatisch                  | Erkennt DOM-Änderungen ohne manuelles Triggern |
| Vielseitig                   | Knoten, Attribute, Text, Struktur             |
| Performant                   | Besser als Polling mit `setInterval`         |
| Erweiterbar                  | Auch in Frameworks & UI-Komponenten nützlich |

---

## 🚀 Wann einsetzen?

- Bei **dynamisch generiertem Content**
- In **Web-Komponenten**
- Für **Live-Aktualisierungen** ohne Reload
- In **Content-Editoren**, **Formularwächtern** oder **SEO-Checkern**

---

## 🔗 Ressourcen

- [MDN – MutationObserver](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)
- [Can I use](https://caniuse.com/?search=mutationobserver) – Sehr gut unterstützt