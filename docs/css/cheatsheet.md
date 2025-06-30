# 🧾 CSS Cheatsheet XXL – Die ultimative Referenz

Ein vollständiger Überblick über essentielle und fortgeschrittene CSS-Techniken.  
Ideal für alle, die produktiv, effizient und professionell gestalten wollen.

---

## 🎨 Farben & Hintergründe

| Eigenschaft             | Beispiel                                |
|-------------------------|------------------------------------------|
| `color`                 | `#333`, `rgb(255, 0, 0)`, `hsl(0, 50%, 50%)` |
| `background-color`      | `transparent`, `rgba(0,0,0,0.5)`        |
| `background-image`      | `url("bild.jpg")`, `linear-gradient(...)` |
| `background-size`       | `cover`, `contain`, `100% 100%`         |
| `background-position`   | `center`, `top left`, `50% 50%`         |
| `background-attachment` | `fixed`, `scroll`                       |
| `filter`                | `blur(3px)`, `contrast(120%)`, `drop-shadow(...)` |

---

## 🔤 Schrift & Text

| Eigenschaft          | Beispiel                             |
|----------------------|----------------------------------------|
| `font-family`        | `"Open Sans", sans-serif`             |
| `font-size`          | `1rem`, `clamp(1rem, 4vw, 2rem)`      |
| `font-weight`        | `normal`, `bold`, `lighter`, `900`   |
| `font-style`         | `italic`, `oblique`                  |
| `letter-spacing`     | `0.1em`, `-0.02em`                    |
| `line-height`        | `1.5`, `120%`                         |
| `text-align`         | `justify`, `center`, `right`         |
| `text-decoration`    | `underline`, `line-through`          |
| `text-shadow`        | `2px 2px 4px #aaa`                    |

---

## 🧩 Selektoren (CSS-Logik)

| Selektor              | Bedeutung                             |
|-----------------------|----------------------------------------|
| `*`                   | alles                                 |
| `#id`                 | Element mit ID                        |
| `.klasse`             | alle mit Klasse                       |
| `element`             | alle Elemente dieses Typs            |
| `div > p`             | direkte Kind-Elemente                |
| `ul li`               | alle Nachfahren                      |
| `div + p`             | direktes Geschwisterelement          |
| `input[type="text"]`  | Attributselektor                     |
| `:not(.hide)`         | Negierung                            |

---

## 🔀 Pseudo-Klassen & -Elemente

| Typ                     | Beispiel                         |
|--------------------------|----------------------------------|
| `:hover`                | bei Mouseover                   |
| `:focus`                | bei aktiver Eingabe             |
| `:first-child`          | erstes Kind                     |
| `:last-of-type`         | letztes Element dieses Typs     |
| `::before` / `::after`  | Inhalte einfügen                |
| `:nth-child(n)`         | gezielter Index                 |

---

## 📦 Box-Modell & Layout

| Eigenschaft          | Beispiel                             |
|----------------------|----------------------------------------|
| `width`, `height`    | `auto`, `100%`, `10rem`              |
| `margin`, `padding`  | `margin: 1rem 2rem;`                 |
| `border`             | `2px solid red`                      |
| `box-sizing`         | `border-box`                         |
| `outline`            | `2px dotted red`                     |
| `overflow`           | `hidden`, `scroll`, `auto`           |

---

## 📐 Position & Display

| Typ                  | Eigenschaften                              |
|----------------------|---------------------------------------------|
| `position`           | `static`, `relative`, `absolute`, `fixed`, `sticky` |
| `top`, `right` etc.  | bei positionierten Elementen               |
| `z-index`            | Stapelreihenfolge                          |
| `display`            | `block`, `inline`, `flex`, `grid`, `none`, `inline-flex` |
| `visibility`         | `hidden`, `visible`, `collapse`            |
| `pointer-events`     | `none`, `auto`                             |

---

## 🧱 Grid & Flexbox

### 📏 Flexbox – 1D Layoutsystem

| Eigenschaft         | Beispiel                               |
|---------------------|------------------------------------------|
| `display`           | `flex`                                 |
| `flex-direction`    | `row`, `column`, `row-reverse`         |
| `justify-content`   | `flex-start`, `center`, `space-between`, `space-around`, `space-evenly` |
| `align-items`       | `stretch`, `center`, `flex-start`, `flex-end`, `baseline` |
| `align-content`     | Für mehrzeilige Container              |
| `flex-wrap`         | `wrap`, `nowrap`, `wrap-reverse`       |
| `flex`              | `1`, `2 1 100px` (grow, shrink, basis) |
| `order`             | `1`, `-1` (Reihenfolge ändern)         |
| `gap`               | `gap: 1rem;`                           |

#### 🧪 Flexbox Beispiel

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}
.item {
  flex: 1 1 200px;
}
```

---

### 📐 CSS Grid – 2D Layoutsystem

| Eigenschaft              | Beispiel                                   |
|--------------------------|--------------------------------------------|
| `display`                | `grid`                                     |
| `grid-template-columns`  | `repeat(3, 1fr)`, `200px auto 1fr`         |
| `grid-template-rows`     | `auto`, `100px auto 1fr`                   |
| `grid-column`, `grid-row`| `1 / 3`, `2 / span 2`                      |
| `grid-area`              | benannte Bereiche                         |
| `gap` / `row-gap` / `column-gap` | `1rem`, `2rem`                  |
| `grid-template-areas`    | z. B. `"head head" "nav main" "foot foot"` |
| `place-items`            | `center`, `start`, `stretch`              |

#### 🧪 Grid Beispiel

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

.item-a {
  grid-column: 1 / span 2;
}

.item-b {
  grid-row: 2 / 4;
}
```

---

### 🆚 Flexbox vs. Grid

| Merkmal                | Flexbox                          | Grid                            |
|------------------------|----------------------------------|---------------------------------|
| Achsen                 | 1D (nur eine Achse)              | 2D (Zeile & Spalte)             |
| Inhalt/Layout-Logik    | Inhalt priorisiert               | Layout priorisiert              |
| Reihenfolge            | mit `order`                      | mit `grid-area`/`grid-*`       |
| Typische Anwendung     | Navigation, UI-Komponenten       | Seitenlayout, komplexe Rastersysteme |


---

## 🖼 Responsive Design

| Technik               | Beispiel                                     |
|------------------------|----------------------------------------------|
| Media Query           | `@media (max-width: 768px) { ... }`         |
| Relative Maße         | `vw`, `vh`, `em`, `rem`, `%`                |
| Dynamische Schriftgrößen | `font-size: clamp(1rem, 2vw, 2rem);`     |
| Mobile First          | CSS ab Basis schreiben, Media Queries für große Screens |

---

## 🎛 Effekte, Animationen & Übergänge

| Eigenschaft           | Beispiel                                 |
|------------------------|------------------------------------------|
| `transition`          | `all 0.3s ease-in-out;`                  |
| `animation`           | `slidein 1s infinite;`                   |
| `transform`           | `scale(1.2)`, `rotate(5deg)`, `translateX(10px)` |
| `@keyframes`          | `@keyframes slidein { from {...} to {...} }` |

---

## 🧰 Utility-Tricks

- **Zentrierung mit Flex:**

```css
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

- **Ellipsis für langen Text:**

```css
.ellipsis {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

- **Responsives Bild:**

```css
img {
  max-width: 100%;
  height: auto;
}
```

---

## 🧠 CSS Custom Properties (Variablen)

```css
:root {
  --main-color: #0d6efd;
  --spacing: 1rem;
}

.button {
  background-color: var(--main-color);
  padding: var(--spacing);
}
```

✅ Wiederverwendbar, leicht zu pflegen, auch für Themes!

---

## ♿ Barrierefreiheit

| Technik            | Beispiel                                  |
|--------------------|-------------------------------------------|
| `aria-label`       | Beschriftung für Screenreader             |
| `alt`              | Alternativtext für Bilder                 |
| `role`             | `role="button"`, `navigation`             |
| `tabindex`         | Steuerung der Tastaturnavigation          |
| `:focus-visible`   | Zeigt Fokus nur bei Tastatur              |

---

## 🧮 Rechenfunktionen

| Funktion        | Beispiel                                 |
|------------------|------------------------------------------|
| `calc()`         | `width: calc(100% - 2rem);`             |
| `min()` / `max()`| `min(100%, 600px)`                      |
| `clamp()`        | `clamp(1rem, 2vw, 2rem)`                |

---

## 🧾 Sonstiges

| Eigenschaft        | Beispiel                              |
|---------------------|----------------------------------------|
| `cursor`            | `pointer`, `move`, `not-allowed`      |
| `user-select`       | `none`, `text`, `auto`                |
| `scroll-behavior`   | `smooth`                              |
| `object-fit`        | `cover`, `contain`                    |
| `aspect-ratio`      | `16 / 9`, `1 / 1`                      |

---

## 📚 Nützliche Ressourcen

- [MDN Web Docs](https://developer.mozilla.org/de/docs/Web/CSS)
- [CSS-Tricks](https://css-tricks.com/)
- [Web.dev – CSS-Lernen](https://web.dev/learn/css/)
- [Can I Use?](https://caniuse.com/)
- [Flexbox Cheat](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)

