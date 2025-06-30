# `<blockquote>` – Zitatblock

## 🧩 Funktion

Das `<blockquote>`-Element wird verwendet, um **längere, wörtlich übernommene Zitate** aus **externen oder internen Quellen** darzustellen.  
Es ist ein **Blockelement**, das üblicherweise **visuell eingerückt** erscheint, um den zitierten Text klar vom restlichen Inhalt abzugrenzen.

> 📌 `<blockquote>` hat eine **semantische Bedeutung**: Es kennzeichnet Inhalte, die **nicht vom Autor selbst stammen**, sondern **übernommen** wurden.

---

## ✅ Verwendung

```html
<blockquote>
  „Der einzige Weg, großartige Arbeit zu leisten, ist, zu lieben, was man tut.“
</blockquote>
```

👉 Der Browser stellt dies standardmäßig eingerückt oder optisch abgesetzt dar.

---

## 🎯 Semantik & Einsatzgebiete

| Zweck                      | Beispiel                            |
|----------------------------|-------------------------------------|
| Zitat aus einem Buch/Text  | „Lorem ipsum…“                      |
| Aussage aus einem Artikel  | „Laut FAZ vom 01.01.2023...“        |
| Redebeiträge / Interviews  | „Ich denke, wir sollten…“           |
| Quelle oder Referenz       | Verlinkung über das `cite`-Attribut |

---

## 🔧 Attribute

| Attribut | Beschreibung |
|----------|--------------|
| `cite`   | Quelle/URL des Zitats (optional, maschinenlesbar) |
| `class`  | Für CSS-Klassen zur visuellen Gestaltung           |
| `id`     | Für interne Verlinkung oder JavaScript-Zugriff     |

---

### Beispiel mit `cite`

```html
<blockquote cite="https://www.example.com/zitatquelle">
  „Vertrauen ist gut, Kontrolle ist besser.“
</blockquote>
```

> 💡 Das `cite`-Attribut verweist **nicht sichtbar im Frontend**, aber es hilft **Suchmaschinen, Screenreadern und Tools**, die Quelle maschinell zu erkennen.

---

## 🎨 Visuelles Styling (CSS)

```css
blockquote {
  border-left: 4px solid #888;
  padding-left: 1em;
  font-style: italic;
  color: #444;
  background-color: #f9f9f9;
}
```

```html
<blockquote>
  „Eine gute Nutzererfahrung beginnt bei semantischem HTML.“
</blockquote>
```

---

## 🧠 Inline-Zitate vs. Block-Zitate

| Zweck               | Element        | Beispiel                              |
|---------------------|----------------|---------------------------------------|
| Längeres Zitat      | `<blockquote>` | für mehrere Sätze oder Absätze        |
| Kurzes Zitat im Text| `<q>`          | „Zitierter Satz“ im Fließtext         |

👉 **Tipp**: Verwende `<q>` für **einzelne Sätze oder Wortgruppen** direkt im Textfluss. `<blockquote>` für **Absätze** oder größere Textteile.

---

## ♿ Barrierefreiheit & Semantik

- Screenreader erkennen `<blockquote>` als Zitat und kündigen es ggf. an (z. B. „Zitat Anfang“)
- Gute Trennung zwischen eigener Meinung und übernommenen Inhalten
- Durch semantische Bedeutung unterstützt es **barrierefreie Navigation** und **besseres SEO**

---

## ❌ Häufige Fehler

| Fehler                                   | Besser                                      |
|------------------------------------------|---------------------------------------------|
| `<blockquote>` für Meinungsäußerung      | Nur verwenden, wenn **wirklich zitiert**    |
| Styling-Zwecke ohne Zitatbedeutung       | Nutze stattdessen `<div class="info">…</div>` |
| Keine Quellenangabe bei übernommenem Text| Wenn möglich, mit `cite`-Attribut arbeiten  |

---

## 📚 Fazit

`<blockquote>` ist das **korrekte HTML-Element für längere Zitate**, die aus anderen Quellen stammen.  
Es trägt zur **semantischen Klarheit**, **Barrierefreiheit** und **strukturellen Qualität** deiner Webseite bei – sowohl für Leser als auch für Maschinen.
