# `<video>` – Video in HTML einbinden

## 🧩 Funktion

Das `<video>`-Element erlaubt es, **Videos direkt in Webseiten einzubetten**, ohne externe Plugins wie Flash. Es unterstützt moderne Formate, eigene Bedienelemente und kann mit JavaScript gesteuert werden.

> 📌 `<video>` ist ein **Block-Element** und bietet volle Kontrolle über Wiedergabe, Lautstärke, Untertitel und mehr.

---

## ✅ Grundverwendung

```html
<video controls width="640" height="360">
  <source src="beispiel.mp4" type="video/mp4" />
  <p>Ihr Browser unterstützt das Video-Tag nicht.</p>
</video>
```

- `controls` zeigt Standard-Bedienelemente
- `<source>` erlaubt mehrere Videoformate zur Kompatibilität
- Alternativer Text wird bei inkompatiblen Browsern angezeigt

---

## 🔧 Attribute im Überblick

| Attribut      | Beschreibung                                                 |
|---------------|--------------------------------------------------------------|
| `src`         | Direktpfad zur Videodatei (optional bei Verwendung von `<source>`) |
| `controls`    | Zeigt Wiedergabeleiste mit Play/Pause, Lautstärke etc.       |
| `autoplay`    | Startet automatisch (benötigt `muted` in modernen Browsern)  |
| `muted`       | Startet stummgeschaltet (z. B. für Autoplay)                 |
| `loop`        | Wiederholt das Video automatisch                             |
| `poster`      | Platzhalterbild vor dem Abspielen                            |
| `preload`     | `auto`, `metadata`, `none` – steuert Ladeverhalten           |
| `width`, `height` | Größe des Players                                        |
| `playsinline` | Startet das Video im Dokumentfluss (v. a. auf iOS)           |

---

## 🎯 Beispiel mit mehreren Quellen

```html
<video controls poster="vorschaubild.jpg" width="800">
  <source src="video.mp4" type="video/mp4" />
  <source src="video.webm" type="video/webm" />
  <p>Ihr Browser unterstützt kein HTML5-Video.</p>
</video>
```

👉 Der Browser verwendet die **erste unterstützte Quelle** – so wird maximale Kompatibilität erreicht.

---

## 🧠 Erweiterte Nutzung: Untertitel und Tracks

```html
<video controls>
  <source src="clip.mp4" type="video/mp4" />
  <track src="untertitel.vtt" kind="subtitles" srclang="de" label="Deutsch" default />
</video>
```

| `<track>` Attribut | Bedeutung                        |
|--------------------|----------------------------------|
| `kind`             | `subtitles`, `captions`, `descriptions`, `chapters`, `metadata` |
| `srclang`          | Sprachcode (z. B. `en`, `de`)    |
| `label`            | Beschriftung im Auswahlmenü      |
| `default`          | Wird standardmäßig aktiviert     |

---

## ♿ Barrierefreiheit (a11y)

- Untertitel und Audiobeschreibungen verbessern Zugänglichkeit
- Ggf. mit `<figure>` und `<figcaption>` kombinieren:

```html
<figure>
  <video controls src="demo.mp4"></video>
  <figcaption>Demovideo zur Produktfunktion</figcaption>
</figure>
```

---

## 🔄 Video vs. andere Medientypen

| Element     | Inhaltstyp       | Interaktiv | Beschreibung                |
|-------------|------------------|------------|-----------------------------|
| `<video>`   | Video             | Ja         | Visuelle Medien mit Ton     |
| `<audio>`   | Audio             | Ja         | Nur Ton, ohne Bild          |
| `<iframe>`  | Eingebettete Seite | Eingeschränkt | Für externe Videoquellen wie YouTube |

---

## 🎨 Styling mit CSS

```css
video {
  max-width: 100%;
  border-radius: 12px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}
```

---

## ❌ Häufige Fehler

| Fehler                             | Besser                                        |
|------------------------------------|-----------------------------------------------|
| Nur ein Format bereitstellen       | Mehrere Formate mit `<source>` einbinden      |
| Kein `controls` oder Fallback-Text | Immer mit Steuerelementen oder Hinweis        |
| Autoplay ohne `muted`              | Moderne Browser erlauben nur stummes Autoplay |

---

## 📚 Fazit

Das `<video>`-Tag macht HTML5 zu einer **vollwertigen Multimedia-Plattform** – ohne Plugins oder externe Player.  
Mit guter Quellenwahl, Untertitelung und sauberem Styling lässt sich ein barrierefreies, reaktionsschnelles Videoerlebnis direkt im Browser schaffen.

> 💬 Als Nächstes: Möchtest du `<audio>`, `<iframe>` oder `<picture>` erkunden?