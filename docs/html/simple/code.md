# `<code>` – Quelltext-/Code-Auszeichnung

## 🧩 Funktion

Das `<code>`-Element dient dazu, **Quelltext, Befehle, Variablen oder Funktionen** inline oder blockweise **semantisch zu kennzeichnen**.  
Es hebt technische Inhalte im Textfluss hervor und macht sie **maschinell erkennbar** – ideal für Dokumentationen, Anleitungen und Entwicklertexte.

> 📌 `<code>` zeigt: „Dieser Text ist Programmcode oder technischer Ausdruck.“  
> Es ist ein **semantisches Inline-Element**, das bei Bedarf mit `<pre>` oder `<samp>` kombiniert werden kann.

---

## ✅ Verwendung (Inline)

```html
<p>Benutze die Funktion <code>print()</code>, um Text in Python auszugeben.</p>
```

👉 Der Ausdruck `print()` wird visuell hervorgehoben (meist mit Monospace-Schrift) und semantisch als Code erkannt.

---

## ✅ Verwendung (Block mit `<pre>`)

```html
<pre><code>
def begruessung():
    print("Hallo Welt!")
</code></pre>
```

👉 Mit `<pre>` bleibt die Formatierung (Einrückung, Zeilen) **genau erhalten** – ideal für mehrzeilige Codeblöcke.

---

## 🔧 Attribute

| Attribut | Beschreibung |
|----------|--------------|
| `class`  | Für CSS-Styling oder Syntax Highlighting (z. B. `class="language-python"`) |
| `id`     | Für JavaScript-Zugriffe oder Linkziele |
| `style`  | Direktes Inline-Styling (z. B. `color`, `background`) |
| `title`  | Optionaler Hinweistext (Tooltip) |

---

## 🎨 Beispiel mit CSS-Styling

```html
<code class="cmd">npm install express</code>
```

```css
.cmd {
  background-color: #f4f4f4;
  color: #c7254e;
  font-family: monospace;
  padding: 2px 4px;
  border-radius: 4px;
}
```

👉 So wird Code in Fließtext visuell hervorgehoben.

---

## 🧠 Unterschied zu verwandten Tags

| Element     | Zweck                                      | Typischer Einsatz                  |
|-------------|--------------------------------------------|------------------------------------|
| `<code>`    | Quelltext & techn. Begriffe                | Inline oder mit `<pre>`            |
| `<pre>`     | Bewahrt Formatierung (Whitespace, Zeilen)  | Für längere, formatierte Blöcke    |
| `<samp>`    | Konsolenausgabe, Beispielausgaben          | z. B. „Zugriff verweigert“         |
| `<kbd>`     | Tastatureingaben                           | z. B. `<kbd>Strg</kbd> + <kbd>S</kbd>` |

---

## 🧪 Weitere Beispiele

### Python-Code in einer Doku

```html
<pre><code class="language-python">
for i in range(5):
    print("Hallo")
</code></pre>
```

### HTML-Tag im Fließtext

```html
<p>Ein Absatz wird mit dem Tag <code>&lt;p&gt;</code> definiert.</p>
```

---

## ♿ Barrierefreiheit & SEO

- Screenreader erkennen `<code>` als Quelltext und **lesen es ggf. anders vor**
- Mit guter Struktur (z. B. `<pre>` + ARIA-Rollen) sind Codebeispiele **besser navigierbar**
- Auch Suchmaschinen erfassen `<code>`-Elemente für **technische Inhalte und Snippets**

---

## ❌ Häufige Fehler

| Fehler                                    | Besser                                         |
|-------------------------------------------|------------------------------------------------|
| Formatierter Code ohne `<pre>`            | `<pre><code>` verwenden für Blockcode         |
| `<code>` für Stilzwecke ohne Bedeutung    | Nur bei echtem Quelltext verwenden            |
| Kombination von `<code>` mit `<b>`/`<i>`  | Lieber semantisch korrekt mit CSS gestalten   |
| Kein Monospace-Styling                    | Browser setzen dies standardmäßig, ggf. ergänzen |

---

## 📚 Fazit

Das `<code>`-Element ist ein zentrales HTML-Werkzeug für **Dokumentation, Tutorials, API-Beschreibungen und technische Blogs**.  
Es sorgt für **klare, semantisch korrekte Kennzeichnung** von Quelltext – in Kombination mit `<pre>`, CSS und ggf. JavaScript auch ideal für **Syntax-Highlighting**.

