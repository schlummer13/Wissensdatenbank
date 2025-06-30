# 🌑 Shadow DOM

## 🧩 Was ist der Shadow DOM?

Der **Shadow DOM** ist ein Teil des DOMs, der **gekapselt** ist – das heißt:

- Er ist **abgeschirmt** vom normalen HTML-Dokument (dem „Light DOM“),
- CSS und JavaScript von außen **gelten darin nicht**,
- und umgekehrt beeinflusst er nicht den globalen DOM.

👉 Shadow DOM ist ein **Grundpfeiler von Web Components**.

---

## 🧠 Warum Shadow DOM?

| Vorteil               | Beschreibung                                 |
|------------------------|----------------------------------------------|
| Kapselung              | HTML, CSS und JS im Shadow DOM sind privat   |
| Kein Style-Leaking     | Styles überschneiden sich nicht gegenseitig |
| Wiederverwendbarkeit   | Saubere Komponenten, keine Namenskonflikte   |
| Testbarkeit            | Leicht isolierbar                            |

---

## 🛠️ Shadow DOM erstellen

```html
<div id="host"></div>
```

```js
const host = document.getElementById("host");

// Shadow Root anfügen
const shadow = host.attachShadow({ mode: "open" });

// Inhalt einfügen
shadow.innerHTML = `
  <style>
    p { color: crimson; }
  </style>
  <p>Ich bin im Shadow DOM</p>
`;
```

---

## 🎭 `mode: "open"` vs. `"closed"`

| Modus     | Bedeutung                              |
|-----------|-----------------------------------------|
| `"open"`  | Zugriff auf `element.shadowRoot` möglich |
| `"closed"`| Kein Zugriff von außen möglich         |

---

## 🔍 Zugriff von außen

```js
host.shadowRoot.querySelector("p").textContent = "Geändert";
```

⚠️ Funktioniert nur bei `"open"`-Modus.

---

## 🧩 Beispiel: Kapselung

```html
<style>
  p { color: blue; }
</style>

<div id="host"></div>
```

```js
const shadow = document.getElementById("host")
  .attachShadow({ mode: "open" });

shadow.innerHTML = `
  <style>
    p { color: red; }
  </style>
  <p>Shadow Inhalt</p>
`;
```

🔸 Ergebnis:  
Der `<p>`-Tag im Shadow DOM ist **rot**, obwohl außen `blue` definiert wurde.

---

## ⚙️ Shadow DOM mit JavaScript erstellen

```js
class MeineBox extends HTMLElement {
  constructor() {
    super();
    const shadow = this.attachShadow({ mode: "open" });
    shadow.innerHTML = `
      <style>
        .rahmen { border: 2px solid black; padding: 1rem; }
      </style>
      <div class="rahmen">
        <slot></slot>
      </div>
    `;
  }
}

customElements.define("meine-box", MeineBox);
```

```html
<meine-box>Hallo in der Box!</meine-box>
```

✅ Ergebnis: Inhalt ist **gekapselt**, aber über `<slot>` sichtbar.

---

## 🕳️ Slot – Sichtbares Loch im Shadow DOM

Ein `<slot>` ist ein **Platzhalter** für Inhalte, die der Benutzer in das Custom Element schreibt.

```js
shadow.innerHTML = `
  <style>slot { color: green; }</style>
  <slot></slot>
`;
```

---

## 🚨 Einschränkungen

- Kein Zugriff mit `querySelectorAll('*')` von außen
- Manche Tools (z. B. jQuery) können kein Shadow DOM
- Barrierefreiheit muss explizit beachtet werden

---

## ✅ Zusammenfassung

| Vorteil                  | Beschreibung                          |
|--------------------------|----------------------------------------|
| Strukturkapselung        | HTML/CSS ist isoliert                  |
| Style Isolation          | Kein Konflikt mit globalem CSS         |
| Web Components Ready     | Perfekte Basis für benutzerdefinierte Tags |
| Erfordert Unterstützung  | Nicht in alten Browsern verfügbar      |

---

## 🔗 Ressourcen

- [MDN – Shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM)
- [Web.dev – Shadow DOM](https://web.dev/shadow-dom/)