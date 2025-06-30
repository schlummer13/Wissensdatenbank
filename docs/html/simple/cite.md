# `<cite>` – Quellennachweis / Urheberangabe

## 🧩 Funktion

Das `<cite>`-Element (Citation) dient dazu, **die Quelle oder den Urheber** eines **zitierten Werks** anzugeben.  
Dies kann der Name eines Autors, eines Buchs, Films, Artikels, Musikstücks, wissenschaftlichen Papiers oder einer Webseite sein.

> 📌 `<cite>` ist ein **semantisches Inline-Element**, das die **Urheberschaft oder Quelle** eines Inhalts kennzeichnet – nicht den Zitattext selbst!

---

## ✅ Verwendung

```html
<blockquote>
  „Der Fortschritt lebt vom Austausch des Wissens.“
  <cite>Albert Einstein</cite>
</blockquote>
```

👉 Der Name „Albert Einstein“ wird als **Urheber der Aussage** ausgezeichnet – das `<cite>` kann auch stilistisch hervorgehoben sein (meist kursiv).

---

## 🔧 Attribute

| Attribut | Beschreibung |
|----------|--------------|
| `class`  | Für visuelles Styling via CSS |
| `style`  | Inline-Styling bei Bedarf     |
| `lang`   | Sprachkennung (z. B. bei fremdsprachigen Werken) |
| `id`     | Für JavaScript oder Ankerlinks |
| `title`  | Tooltip für Zusatzinfos        |

---

## 🎨 Beispiel: Artikelzitierung

```html
<p>
  Mehr zum Thema im Artikel 
  <cite>„Die Zukunft der KI“</cite> von 
  <strong>Dr. Julia Weber</strong>, erschienen in der FAZ.
</p>
```

👉 Das Werk wird mit `<cite>` markiert, die Person ggf. mit `<strong>` oder Text.

---

## 📚 Gültige Inhalte für `<cite>`

Laut HTML-Spezifikation eignet sich `<cite>` für:

- **Buch- oder Artikeltitel**
- **Filme, Serien, Videos**
- **Lieder oder Musikstücke**
- **Webseiten oder Blogposts**
- **Wissenschaftliche Arbeiten**
- **Gemälde, Kunstwerke, Theaterstücke**

### ✅ Beispiel: Webseite zitieren

```html
<p>Weitere Informationen findest du auf <cite>MDN Web Docs</cite>.</p>
```

### ✅ Beispiel: Buch zitieren

```html
<p>In <cite>Designing Data-Intensive Applications</cite> wird erklärt, wie verteilte Systeme funktionieren.</p>
```

---

## ⚠️ Achtung: Nicht für „Zitate“ selbst

| Situation                                | Element |
|------------------------------------------|---------|
| Inhalt des Zitats                        | `<q>` oder `<blockquote>` |
| Quelle oder Urheber des Zitats           | `<cite>` |
| Text ohne Urheberbezug                   | Kein `<cite>` nötig |

---

## ♿ Barrierefreiheit & SEO

- `<cite>` gibt Screenreadern und Suchmaschinen **zusätzliche semantische Hinweise** über Urheberschaft
- Es verbessert die Struktur von Inhalten und kann in **strukturierte Datenformate** wie JSON-LD eingebunden werden

---

## ❌ Häufige Fehler

| Fehler                                     | Korrekte Alternative                          |
|--------------------------------------------|-----------------------------------------------|
| `<cite>` für markierte Textstellen ohne Quelle | Nutze `<mark>`, `<strong>` oder `<em>` stattdessen |
| Keine Auszeichnung von Werk- oder Urhebern | Verwende `<cite>`, wo es inhaltlich passt     |
| `<cite>` um ganzen Absatz                 | `<cite>` ist ein **Inline-Element**, nicht blockbasiert |

---

## 📚 Fazit

Das `<cite>`-Element bietet eine **semantisch saubere und barrierefreie Möglichkeit**, um **Quellen, Urheber oder Werke** kenntlich zu machen.  
Es ist wichtig für **strukturierte Inhalte, wissenschaftliche Texte, Blogbeiträge** und allgemein alle Inhalte, bei denen die **Ursprungsquelle** hervorgehoben werden sollte.
