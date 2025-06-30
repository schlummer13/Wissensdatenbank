# 🧾 DOM – HTML-Inhalte bearbeiten

## 🧩 Was bedeutet „HTML über das DOM steuern“?

Mit JavaScript kannst du HTML-Inhalte **lesen, verändern, ersetzen oder dynamisch erzeugen** – direkt im laufenden Browserfenster.  
Du brauchst dafür nur DOM-Methoden wie `innerHTML`, `createElement`, `appendChild`, `remove()` usw.

---

## 📌 Häufige Methoden & Eigenschaften

| Eigenschaft / Methode   | Beschreibung                                       |
|--------------------------|----------------------------------------------------|
| `innerHTML`              | Liest oder ersetzt den gesamten HTML-Inhalt       |
| `textContent`            | Liest/ändert nur den reinen Text (ohne HTML)      |
| `innerText`              | Wie `textContent`, aber abhängig vom sichtbaren Layout |
| `outerHTML`              | Liest oder ersetzt das gesamte Element inkl. Tag  |

---

## 🖋 Inhalte setzen und ersetzen

### 🔹 Beispiel 1: `innerHTML`

```js
const box = document.getElementById("info");
box.innerHTML = "<p><strong>Wichtig!</strong> Lies das.</p>";
```

### 🔹 Beispiel 2: `textContent`

```js
box.textContent = "<p>Kein HTML</p>"; // Gibt reinen Text aus
```

---

## 🧱 Neue HTML-Elemente erzeugen

```js
const absatz = document.createElement("p");
absatz.textContent = "Ich bin ein dynamischer Absatz.";

document.body.appendChild(absatz);
```

---

## ➕ HTML kombinieren

Du kannst vorhandenes HTML **ergänzen**, nicht nur ersetzen:

```js
const container = document.querySelector(".liste");

container.innerHTML += "<li>Neuer Eintrag</li>";
```

⚠️ Vorsicht bei `innerHTML += ...`: Es rendert den ganzen Inhalt neu – nicht ideal bei Performance.

---

## 🔄 Elemente kopieren (Klonen)

```js
const original = document.querySelector(".card");
const kopie = original.cloneNode(true); // true = inklusive Inhalt
document.body.appendChild(kopie);
```

---

## 🗑 HTML entfernen

```js
const zuLöschen = document.querySelector(".hinweis");
zuLöschen.remove();
```

---

## 🧪 Beispiel: Dynamische Liste erzeugen

```js
const liste = document.createElement("ul");

["HTML", "CSS", "JavaScript"].forEach(tech => {
  const li = document.createElement("li");
  li.textContent = tech;
  liste.appendChild(li);
});

document.body.appendChild(liste);
```

---

## 🎨 HTML strukturieren per DOM

```js
const artikel = document.createElement("article");

artikel.innerHTML = `
  <h2>Neues Feature</h2>
  <p>Dieses Feature ist super.</p>
`;

document.body.appendChild(artikel);
```

---

## ✅ Zusammenfassung

| Aktion                   | Methode/Eigenschaft             |
|---------------------------|--------------------------------|
| HTML setzen               | `element.innerHTML = "..."`    |
| Text setzen               | `element.textContent = "..."`  |
| Element erstellen         | `document.createElement()`     |
| Anhängen                  | `appendChild()`, `append()`    |
| Entfernen                 | `remove()`, `removeChild()`    |
| Klonen                    | `cloneNode(true)`              |
