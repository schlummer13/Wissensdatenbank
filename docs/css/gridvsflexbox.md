# ⚔️ CSS Grid vs. Flexbox – Wann nutze ich was?

## 🧩 Warum vergleichen?

Sowohl **Flexbox** als auch **CSS Grid** sind moderne Layoutsysteme in CSS.  
Sie lösen viele Probleme der klassischen Layoutmethoden (`float`, `table`, `inline-block`) – **jedoch mit unterschiedlichen Ansätzen und Einsatzbereichen**.

---

## 🔍 Übersicht

| Kriterium               | Flexbox                        | CSS Grid                                 |
|-------------------------|--------------------------------|-------------------------------------------|
| Achsen                  | 1D: **nur Zeile ODER Spalte**  | 2D: **Zeile UND Spalte** gleichzeitig     |
| Ausrichtung             | sequentiell                    | tabellarisch / rasterartig                |
| Layout-Typ              | Inhaltsbasiert (Content-first) | Strukturbasiert (Layout-first)            |
| Elementreihenfolge      | leicht steuerbar mit `order`   | auch steuerbar mit `grid-area`            |
| Responsives Verhalten   | sehr einfach                   | etwas komplexer, aber leistungsfähig      |
| Gitterstruktur          | nicht möglich                  | nativ mit `grid-template-*`, `fr`, etc.   |
| Nesting-Unterstützung   | sehr gut                       | sehr gut                                   |
| Browserunterstützung    | ✅ Sehr gut                     | ✅ Sehr gut (seit 2017)                    |

---

## 🎯 Wann solltest du Flexbox verwenden?

✅ **Reihen oder Spalten**  
✅ Dynamische Inhaltselemente  
✅ Navigationen, Toolbars, Buttons  
✅ Zentrierung in einer Richtung  
✅ Wenn du keine exakte Spaltenstruktur brauchst

### Beispiel:

```css
nav {
  display: flex;
  justify-content: space-between;
}
```

---

## 🎯 Wann solltest du CSS Grid verwenden?

✅ **Komplexe Layouts mit Zeilen UND Spalten**  
✅ Raster für Bilder, Artikel, Dashboard-Widgets  
✅ Genaue Positionierung über Gridlinien  
✅ Wenn das **Layout im Vordergrund** steht (nicht der Inhalt)

### Beispiel:

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: auto auto;
}
```

---

## 🧠 Kombinieren von Grid und Flex

Flexbox und Grid **ergänzen sich hervorragend**.  
Ein typischer Anwendungsfall:

```html
<div class="grid-container">
  <div class="card">
    <div class="card-header">…</div>
    <div class="card-body">…</div>
    <div class="card-footer">…</div>
  </div>
</div>
```

```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
}

.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
```

➡️ **Grid** für das übergeordnete Layout  
➡️ **Flexbox** innerhalb von Komponenten

---

## 📊 Visualer Vergleich

| Feature                         | Flexbox            | Grid             |
|----------------------------------|---------------------|------------------|
| Zentrierung mit 1 Zeile         | ✅ Einfach           | ✅ Möglich        |
| Galerie mit mehreren Zeilen     | 🔸 Umständlich       | ✅ Optimal        |
| Dynamische Spaltenanzahl        | 🔸 Workaround nötig  | ✅ mit `auto-fit` |
| Elemente in bestimmter Position | 🔸 `order`-basiert   | ✅ mit `grid-area`|
| Layout mit „Lücken“             | 🔸 schwierig         | ✅ natürlich      |

---

## 🚫 Häufige Missverständnisse

| Irrtum                                | Realität                                         |
|----------------------------------------|--------------------------------------------------|
| „Flexbox ist veraltet wegen Grid“     | ❌ Beide sind moderne, komplementäre Tools        |
| „Grid ist nur für große Layouts“      | ❌ Grid funktioniert auch für kleine Komponenten  |
| „Grid ist komplizierter“              | 🔸 Anfangs ja, aber bietet mehr Kontrolle         |

---

## 📚 Fazit

| Wenn du brauchst …                | Nutze …   |
|-----------------------------------|-----------|
| einfache, lineare Ausrichtung     | ✅ Flexbox |
| komplexe, strukturierte Raster    | ✅ Grid    |
| maximale Kontrolle über Platzierung | ✅ Grid  |
| schnelle, mobile-first Struktur   | ✅ Flexbox |

> 💡 Tipp: **Beginne mit dem Layout (Grid), verfeinere Inhalte mit Flexbox**
