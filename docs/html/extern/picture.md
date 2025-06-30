# `<picture>` – Responsive Bilder einbinden

## 🧩 Funktion

Das `<picture>`-Element ermöglicht die **Einbindung responsiver Bilder**, die sich je nach Bildschirmgröße, Auflösung oder Dateiformat automatisch anpassen.  
So können beispielsweise auf kleinen Geräten kleinere Bilder oder modernere Formate (wie WebP oder AVIF) bevorzugt geladen werden.

> 📌 `<picture>` gibt dem Browser mehr Flexibilität bei der Auswahl der besten Bildquelle – für **Performance, Qualität und Kontrolle**.

---

## ✅ Grundverwendung

```html
<picture>
  <source srcset="bild.webp" type="image/webp" />
  <source srcset="bild.jpg" type="image/jpeg" />
  <img src="bild.jpg" alt="Beispielbild" />
</picture>
```

- Der Browser wählt den **ersten passenden `<source>`-Eintrag**
- `<img>` dient als **Fallback** und liefert `alt`, `width`, `height` etc.

---

## 🔧 Struktur und Attribute

### `<picture>`

- Container für eine oder mehrere `<source>`-Elemente
- Keine eigenen Attribute – wird über `<img>` und `<source>` gesteuert

### `<source>`

| Attribut     | Bedeutung                                                  |
|--------------|-------------------------------------------------------------|
| `srcset`     | Pfad zur Bildquelle                                         |
| `type`       | Bildformat (`image/webp`, `image/jpeg`, ...)               |
| `media`      | Media Query (z. B. `min-width`, `max-width`, etc.)         |
| `sizes`      | Optionale Angabe für Layoutgröße (nur bei `srcset` mit Größen) |

### `<img>`

- Pflicht innerhalb von `<picture>`
- Muss ein `alt`-Attribut enthalten
- Wird verwendet, wenn kein `<source>` passt

---

## 🖼️ Beispiel: Bild nach Viewport-Größe wechseln

```html
<picture>
  <source srcset="bild-large.webp" media="(min-width: 1024px)" type="image/webp" />
  <source srcset="bild-medium.jpg" media="(min-width: 600px)" type="image/jpeg" />
  <img src="bild-small.jpg" alt="Ein schöner Ausblick" width="800" height="600" />
</picture>
```

👉 Je nach Viewport lädt der Browser ein kleines, mittleres oder großes Bild.

---

## 📱 Beispiel mit Retina-Support

```html
<picture>
  <source srcset="bild@2x.webp 2x, bild.webp 1x" type="image/webp" />
  <img src="bild.jpg" alt="Produktabbildung" />
</picture>
```

👉 Retina-Displays bekommen die höher aufgelöste Variante (2x), normale Geräte die Standardversion (1x).

---

## ♿ Barrierefreiheit

- Das `alt`-Attribut im `<img>` ist **verpflichtend**
- `<picture>` selbst hat **keine semantische Bedeutung**
- Optional mit `<figure>` kombinierbar:

```html
<figure>
  <picture>
    <source srcset="portrait.webp" type="image/webp" />
    <img src="portrait.jpg" alt="Florian Fenzl" />
  </picture>
  <figcaption>Portrait von Florian Fenzl</figcaption>
</figure>
```

---

## 🧠 Wann `<picture>` verwenden?

| Use Case                      | Geeignet? |
|-------------------------------|-----------|
| Responsive Images             | ✅ Ja     |
| Retina-Optimierung            | ✅ Ja     |
| Browserformat-Kompatibilität | ✅ Ja     |
| Nur einfache Bilder anzeigen  | ❌ Lieber direkt `<img>` |

---

## ❌ Häufige Fehler

| Fehler                             | Empfehlung                                       |
|------------------------------------|--------------------------------------------------|
| Kein `<img>`-Fallback              | Immer am Ende `<img>` verwenden                  |
| `type` oder `media` vergessen      | Führt zu fehlerhafter Auswahl                    |
| Nur Desktop-Version eingebunden   | Mobile-First: auch kleine Versionen anbieten     |

---

## 🔄 Vergleich: `<picture>` vs. `srcset`

| Technik         | Vorteile                                    | Einschränkungen                             |
|------------------|---------------------------------------------|----------------------------------------------|
| `<img srcset>` | Einfacher Syntax, schnelle Integration       | Kein Wechsel des Formats möglich             |
| `<picture>`     | Voll flexibel: Format + Media Queries       | Etwas komplexer in der Struktur              |

---

## 📚 Fazit

Das `<picture>`-Element ist ein leistungsstarkes HTML-Feature zur **Optimierung von Bildern** für verschiedene Bildschirmgrößen, Geräte und Formate.  
Besonders in Zeiten von **Mobile First** und **Page Speed Optimierung** ist der gezielte Einsatz von `<picture>` ein echter Pluspunkt.
