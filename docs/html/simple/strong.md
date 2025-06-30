# `<strong>` – Wichtige Textauszeichnung

## 🧩 Funktion

Das `<strong>`-Element dient dazu, **Text inhaltlich hervorzuheben**, der **besonders wichtig** oder **relevant** ist.  
Es unterscheidet sich von rein visueller Hervorhebung (z. B. durch `<b>`) dadurch, dass es auch **semantische Bedeutung** hat.

> 📌 **Screenreader betonen `<strong>`-Text** akustisch oder visuell, weil er als **wichtig** markiert ist.

---

## ✅ Verwendung

```html
<p>Bitte <strong>vergiss nicht</strong>, das Formular abzusenden!</p>
```

👉 In diesem Fall weist der Satz auf etwas Wichtiges hin – `<strong>` unterstreicht das **inhaltliche Gewicht**.

---

## 🎯 Bedeutung & Semantik

| Merkmal              | Beschreibung |
|----------------------|--------------|
| **Semantisch wichtig** | Betont **inhaltliche Wichtigkeit**, nicht bloß visuelles Styling |
| **Barrierefrei**     | Screenreader lesen `<strong>` mit **betonter Stimme** |
| **SEO-relevant**     | Wird von Suchmaschinen als **gewichteter Text** wahrgenommen |
| **Inline-Element**   | Kann **innerhalb von Absätzen oder Sätzen** verwendet werden |

---

## 🔧 Attribute

| Attribut | Beschreibung |
|----------|--------------|
| `class`  | CSS-Styling für visuelle Anpassungen |
| `style`  | Inline-Styling (z. B. `color`, `font-weight`) |
| `id`     | JS-Zugriff oder direkte Verlinkung |
| `lang`   | Sprachkennung für den Inhalt innerhalb der Hervorhebung |

---

## 🎨 Beispiel mit CSS

```html
<p>
  Dieses Produkt ist <strong class="highlight">nur noch heute</strong> zum Sonderpreis erhältlich.
</p>
```

```css
.highlight {
  color: darkred;
  background-color: #fff1f1;
  font-weight: bold;
  padding: 0 4px;
}
```

---

## 📐 Unterschied zu `<b>`

| Element     | Semantik         | Bedeutung für Screenreader / SEO |
|-------------|------------------|----------------------------------|
| `<strong>`  | Ja ✅             | Wird als wichtig markiert        |
| `<b>`       | Nein ❌           | Nur optisch fett                 |

👉 Verwende `<strong>`, wenn du **eine Aussage oder ein Wort inhaltlich hervorheben** willst. Nutze `<b>` nur für rein visuelle Hervorhebungen **ohne semantische Relevanz** (z. B. im Layout, technischen UIs).

---

## ♿ Barrierefreiheit

- **Screenreader sprechen den Text betonter** aus oder machen eine kurze Pause.
- Ideal für **Warnungen, Hinweise, Befehle, Anweisungen, Regeln, Pflichtangaben**.
- Auch für Überschriften oder Labels innerhalb von Formularen sinnvoll.

---

## ❌ Häufige Fehler

| Fehler                                         | Besser                                       |
|-----------------------------------------------|----------------------------------------------|
| Verwendung nur zum „fett machen“              | Nutze CSS oder `<b>` stattdessen             |
| Einsatz für unbedeutende dekorative Texte     | `<strong>` nur bei **inhaltlicher Bedeutung** |
| `<strong>` als Blockelement                   | Es ist ein **Inline-Element** – für Textteile, keine Absätze |

---

## 📚 Fazit

Das `<strong>`-Tag ist die **semantisch korrekte Wahl für wichtige Textpassagen**.  
Es sollte gezielt und sparsam eingesetzt werden, um **Bedeutung zu vermitteln**, nicht nur Stil. In Kombination mit CSS kann es sowohl **funktional als auch optisch** wirksam sein.
