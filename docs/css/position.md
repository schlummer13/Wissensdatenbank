# 📍 CSS-Positionierung – Elemente gezielt platzieren

## 🧩 Was bedeutet „Positionierung“ in CSS?

Mit CSS-Positionierung steuerst du **präzise**, **wo** ein Element auf der Seite erscheinen soll – unabhängig vom normalen Dokumentfluss.  
Die zentrale Eigenschaft dafür ist:

```css
position: static | relative | absolute | fixed | sticky;
```

Jeder Wert verändert das Verhalten eines Elements in Bezug auf seine Umgebung.

---

## 🔸 Übersicht: Positionierungsarten

| Wert       | Beschreibung                                                 |
|------------|--------------------------------------------------------------|
| `static`   | Standard-Layout, im normalen HTML-Fluss                      |
| `relative` | Verschiebung relativ zur ursprünglichen Position             |
| `absolute` | Position relativ zum nächstgelegenen positionierten Vorfahren |
| `fixed`    | Fixiert im Viewport (z. B. immer sichtbar)                   |
| `sticky`   | Mischung aus `relative` und `fixed` – klebt bei Scroll       |

---

## 🔹 `static` (Standard)

```css
position: static;
```

- **Standardwert für alle Elemente**
- Keine Verschiebung möglich mit `top`, `left`, etc.
- Orientiert sich am normalen **Dokumentenfluss**

---

## 🔹 `relative`

```css
position: relative;
top: 10px;
left: 20px;
```

- Element bleibt im Layoutfluss  
- **Wird visuell verschoben**, ohne Nachbarelemente zu beeinflussen  
- **Bezugsrahmen ist die eigene Originalposition**

---

## 🔹 `absolute`

```css
position: absolute;
top: 0;
left: 0;
```

- Entfernt das Element aus dem normalen Fluss  
- **Bezieht sich auf das nächste übergeordnete Element mit `position` ≠ `static`**  
- Falls kein solches vorhanden ist, bezieht es sich auf `<html>`

> ✅ Kombiniere mit `position: relative;` beim Container für saubere Kontrolle

```html
<div class="container">
  <div class="box">Ich bin absolut positioniert</div>
</div>
```

```css
.container {
  position: relative;
}

.box {
  position: absolute;
  bottom: 0;
  right: 0;
}
```

---

## 🔹 `fixed`

```css
position: fixed;
top: 0;
left: 0;
```

- Bezieht sich **immer auf den Viewport** (Fenster)  
- **Scrollt nicht mit** – ideal für Sticky-Navigationsleisten, Buttons o.Ä.
- Praktisch für: Cookie-Hinweise, Header, „Zurück nach oben“-Links

---

## 🔹 `sticky`

```css
position: sticky;
top: 0;
```

- **Klebt** am angegebenen Rand (`top`, `left`...)  
- Beginnt wie `relative`, wird aber beim Scrollen `fixed`  
- Nur innerhalb des übergeordneten Containers sichtbar  
- Container muss eine definierte Höhe besitzen

> ⚠️ Funktioniert **nur bei scrollbarem Elternbereich** – ideal für Abschnittsnavigationen oder Tabellenüberschriften

---

## 📐 Zusätzliche Positions-Eigenschaften

| Eigenschaft | Bedeutung                                 |
|-------------|--------------------------------------------|
| `top`       | Abstand von der oberen Kante              |
| `right`     | Abstand von der rechten Kante             |
| `bottom`    | Abstand von der unteren Kante             |
| `left`      | Abstand von der linken Kante              |
| `z-index`   | Stapelreihenfolge (höherer Wert = vorne)  |

---

## 🎯 Beispiel: Sticky Navbar

```html
<header class="sticky-header">
  <h1>Meine Website</h1>
</header>
```

```css
.sticky-header {
  position: sticky;
  top: 0;
  background: white;
  z-index: 1000;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
```

---

## ❌ Häufige Fehler

| Fehler                                | Besser                                             |
|---------------------------------------|----------------------------------------------------|
| `absolute` ohne `relative`-Eltern     | Immer ein Kontext-Element mit `position: relative` |
| `sticky` funktioniert nicht           | Eltern-Element braucht definierte Höhe             |
| `z-index` hat keine Wirkung           | Nur bei `position` ≠ `static` wirksam              |

---

## 🧠 Wann verwende ich was?

| Ziel                            | Empfohlene Positionierung |
|----------------------------------|----------------------------|
| Normales Layout                 | `static` (Standard)        |
| Leichte Verschiebung            | `relative`                 |
| Überlagerung / Layer            | `absolute` + `z-index`     |
| Immer sichtbar, Viewport-fixiert | `fixed`                   |
| Kleben bei Scroll               | `sticky`                   |

---

## 📚 Fazit

Die CSS-Positionierung ist ein zentrales Werkzeug zur **Gestaltung moderner Layouts, UI-Komponenten und responsiver Interfaces**.  
Wer ihre Unterschiede kennt, kann **präzise, flexible und performante Designs** erstellen – vom Sticky Header bis zum Modalfenster.