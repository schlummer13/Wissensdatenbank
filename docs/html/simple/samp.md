# `<samp>` – Beispielausgabe (Sample Output)

## 🧩 Funktion

Das `<samp>`-Element (Sample Output) zeigt die **Ausgabe eines Programms, einer Konsole oder eines Systems**.  
Es stellt typischerweise eine **Antwort oder ein Resultat** dar – meist im Monospace-Stil.

> 📌 Für Entwickler:innen-Dokumentation oder CLI-Beispiele sehr sinnvoll.

---

## ✅ Verwendung

```html
<p>Nach dem Login zeigt das System:</p>
<pre><samp>Willkommen, Benutzer!</samp></pre>
```

---

## 🔧 Attribute

| Attribut | Beschreibung        |
|----------|---------------------|
| `class`  | Für Design (z. B. „output“) |
| `id`     | JS oder Linkziele   |
| `style`  | Direktes Styling     |

---

## 🎨 Beispiel mit CSS

```css
samp {
  color: #006400;
  background-color: #f4f4f4;
  font-family: monospace;
}
```

---

## 🧠 Einsatzszenarien

- Terminalausgabe (z. B. Fehlermeldung)
- Log-Einträge
- API-Responses
- Debug-Ausgaben

---

## ❌ Fehler vermeiden

| Fehler              | Besser                                    |
|---------------------|--------------------------------------------|
| Nur `<pre>` für Output | Kombiniere mit `<samp>` für Semantik     |
| `<samp>` für Benutzereingaben | Dafür lieber `<kbd>` verwenden      |

---

## 📚 Fazit

Verwende `<samp>`, wenn du **Ausgaben aus Programmen oder Systemen realistisch darstellen** willst – besonders nützlich für technische Dokus.