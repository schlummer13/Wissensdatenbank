# `<button>` – Interaktive Schaltfläche

## 🧩 Funktion

Das `<button>`-Element erzeugt eine **klickbare Schaltfläche**, die für verschiedene Zwecke eingesetzt werden kann – zum Beispiel:

- zum **Absenden** oder **Zurücksetzen** eines Formulars,
- für **Interaktionen per JavaScript** (z. B. Öffnen eines Modals),
- oder als allgemeiner **Trigger** für clientseitige Logik.

> 📌 `<button>` ist ein **vollwertiges semantisches Element**, das standardmäßig Fokus-, Tastatur- und ARIA-Unterstützung bietet.

---

## ✅ Verwendung

### Formular-Schaltfläche

```html
<form action="/absenden" method="post">
  <input type="email" name="email" required />
  <button type="submit">Absenden</button>
</form>
```

### Interaktive Schaltfläche mit JavaScript

```html
<button type="button" onclick="alert('Hallo Welt!')">Klick mich</button>
```

---

## 🔧 Attribute

| Attribut   | Beschreibung                                                             |
|------------|--------------------------------------------------------------------------|
| `type`     | Bestimmt die Funktion: `submit`, `reset` oder `button` (Standard: `submit`) |
| `disabled` | Deaktiviert die Schaltfläche – keine Interaktion möglich                 |
| `name`     | Formularschlüssel, wird beim Absenden übermittelt                        |
| `value`    | Wert, der zusammen mit dem Namen gesendet wird                           |
| `form`     | Verknüpft Button mit externem Formular (außerhalb des `<form>`-Tags)     |
| `autofocus`| Setzt automatisch den Fokus auf den Button beim Laden                    |
| `aria-`    | ARIA-Rollen und Zustände für Barrierefreiheit                            |

---

## 🎯 Typische `type`-Werte

| Wert       | Bedeutung                                     |
|------------|-----------------------------------------------|
| `submit`   | Sendet das Formular (Standardwert)            |
| `reset`    | Setzt alle Felder im Formular zurück          |
| `button`   | Keine Standardaktion – benötigt JS-Logik      |

---

## 🎨 Beispiel mit CSS

```html
<button class="cta">Jetzt starten</button>
```

```css
button.cta {
  background-color: #0057b8;
  color: white;
  border: none;
  padding: 0.8rem 1.2rem;
  font-size: 1rem;
  border-radius: 6px;
  cursor: pointer;
}
```

---

## ♿ Barrierefreiheit

- `<button>` ist **nativ barrierefrei**: Fokusfähig, mit Tastatur nutzbar, durch Screenreader erkannt
- `aria-label` kann verwendet werden, um die Funktion genauer zu beschreiben:

```html
<button aria-label="Suchmenü öffnen">
  🔍
</button>
```

---

## 🧠 Unterschied zu `<input type="submit">`

| Kriterium             | `<button>`                      | `<input type="submit">`      |
|------------------------|----------------------------------|-------------------------------|
| Inhalte               | Text, HTML, Symbole erlaubt     | Nur Text über `value`        |
| Styling               | Flexibler durch HTML-Struktur   | Weniger Gestaltungsspielraum |
| Barrierefreiheit      | Beide gut, aber `<button>` flexibler |
| Kombinierbar mit Icons| Ja                              | Nein                         |

---

## ❌ Häufige Fehler

| Fehler                              | Besser                                         |
|-------------------------------------|------------------------------------------------|
| Kein `type` angegeben               | Immer `type="button"` bei nicht-Formularbuttons |
| Nur Text ohne Kontext               | Sinnvolle Labels verwenden                     |
| Styling mit `<a>` als Button        | Lieber echtes `<button>` nutzen (semantisch korrekt) |

---

## 📚 Fazit

`<button>` ist ein vielseitiges, zugängliches und modernes HTML-Element für Interaktionen aller Art.  
Mit dem richtigen `type` und sinnvoller Beschriftung lässt sich damit **fast jede Aktion** im Web auslösen – von Formulareingaben bis UI-Trigger.

