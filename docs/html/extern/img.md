# `<img>` – Bild in HTML einfügen

## 🧩 Funktion

Das `<img>`-Element wird verwendet, um **grafische Inhalte** wie Fotos, Illustrationen, Icons oder Diagramme auf einer Webseite anzuzeigen.  
Es ist ein **leeres (self-closing)** Inline-Element, das keine inneren Inhalte besitzt, aber über Attribute gesteuert wird.

> 📌 Bilder erhöhen die visuelle Attraktivität, unterstützen Inhalte – und sind ein zentraler Bestandteil moderner Webseiten.

---

## ✅ Grundverwendung

```html
<img src="bild.jpg" alt="Beschreibung des Bildes" />
```

- `src` ist der Pfad zum Bild (relativ oder absolut)
- `alt` ist ein verpflichtender Alternativtext – wichtig für Barrierefreiheit und SEO

---

## 🔧 Attribute im Überblick

| Attribut       | Beschreibung                                                   |
|----------------|----------------------------------------------------------------|
| `src`          | Pfad zur Bilddatei (lokal oder URL)                            |
| `alt`          | Alternativtext (wird angezeigt, wenn Bild nicht geladen wird)  |
| `title`        | Zusätzliche Beschreibung als Tooltip bei Mouseover             |
| `width` / `height` | Bildgröße in Pixel (empfohlen für Layout-Stabilität)       |
| `loading`      | `lazy` für verzögertes Nachladen, `eager` für sofortiges Laden |
| `srcset`       | Alternativen für responsive Bilder                             |
| `sizes`        | Unterstützt `<srcset>` zur Größenoptimierung                   |
| `decoding`     | Bilddecodierung: `sync`, `async`, `auto`                       |
| `referrerpolicy` | Steuert HTTP-Referrer bei externen Bildern                  |

---

## 🖼️ Beispiel mit festen Dimensionen

```html
<img src="team.jpg" alt="Teamfoto" width="600" height="400" />
```

---

## 🧠 Responsive Varianten mit `srcset`

```html
<img 
  src="bild-klein.jpg" 
  srcset="bild-gross.jpg 1024w, bild-medium.jpg 640w" 
  sizes="(max-width: 600px) 100vw, 50vw"
  alt="Landschaft bei Sonnenuntergang" 
/>
```

👉 Der Browser wählt das passende Bild je nach Bildschirmgröße und Auflösung.

---

## ♿ Barrierefreiheit (a11y)

| Element | Funktion                                                |
|---------|---------------------------------------------------------|
| `alt`   | Muss klar und treffend beschreiben, was auf dem Bild zu sehen ist |
| Leeres `alt=""` | Verwenden für dekorative Bilder (z. B. Icons)    |
| `title`| Optional – aber kein Ersatz für `alt`                    |

**Beispiele für gutes `alt`:**

- ✔️ `alt="Porträt von Florian Fenzl"`  
- ✔️ `alt="Diagramm mit Quartalszahlen 2025"`  
- ❌ `alt="bild123.jpg"` – unbrauchbar für Screenreader

---

## 📦 Ladeverhalten optimieren

- **`loading="lazy"`** verbessert die Performance bei vielen Bildern
- Bilder sollten **vorab dimensioniert** werden (z. B. mit `width`/`height`)
- Moderne Formate wie **WebP** oder **AVIF** bieten bessere Komprimierung

```html
<img 
  src="banner.webp" 
  alt="Headergrafik mit Logo" 
  width="1200" 
  height="400" 
  loading="lazy"
/>
```

---

## ❌ Häufige Fehler

| Fehler                                  | Besser                                                |
|-----------------------------------------|--------------------------------------------------------|
| Kein `alt`-Text                         | Immer `alt` verwenden – auch für dekorative Inhalte    |
| Layout mit Bildern erzwingen           | Dafür CSS nutzen                                      |
| Große Bilder ohne Optimierung einbinden| Vorher skalieren und komprimieren                     |
| `<img>` ohne `width`/`height`          | Führt zu Layout-Sprüngen – besser mit festen Größenangaben |

---

## 🔄 Vergleich: `<img>` vs. CSS-Hintergrund

| Zweck                     | `<img>`                            | CSS `background-image`              |
|---------------------------|-------------------------------------|-------------------------------------|
| Sichtbarer Inhalt         | Ja                                  | Nein (rein dekorativ)               |
| SEO / Barrierefreiheit    | Ja, mit `alt`-Text                  | Nein                                |
| Skalierung / Positionierung| Eingeschränkt                      | Sehr flexibel über CSS              |

---

## 📚 Fazit

Das `<img>`-Tag ist essenziell zur Integration visueller Inhalte in HTML-Seiten.  
Mit sinnvollen Attributen, barrierefreiem `alt`-Text und moderner Optimierung trägt es maßgeblich zur **Nutzererfahrung, Performance und SEO** bei.
