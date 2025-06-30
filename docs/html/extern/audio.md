# `<audio>` – Audioinhalte einbinden

## 🧩 Funktion

Mit dem `<audio>`-Element lassen sich **Audiodateien direkt im Browser abspielen**, ohne externe Plugins. Es eignet sich für Musik, Podcasts, Soundeffekte, Voice-Overs und vieles mehr.

> 📌 `<audio>` ist ein semantisches HTML5-Element und bietet native Steuerelemente, Event-Handling via JavaScript sowie Unterstützung für moderne Audioformate.

---

## ✅ Grundverwendung

```html
<audio controls>
  <source src="beispiel.mp3" type="audio/mpeg" />
  <p>Ihr Browser unterstützt das Audio-Element nicht.</p>
</audio>
```

- `controls` zeigt Bedienelemente wie Play/Pause und Lautstärke
- `<source>` erlaubt mehrere Formate zur Kompatibilität
- Fallback-Text für nicht unterstützende Browser

---

## 🔧 Attribute

| Attribut      | Beschreibung                                                     |
|---------------|------------------------------------------------------------------|
| `src`         | Pfad zur Audiodatei (kann auch über `<source>` definiert werden) |
| `controls`    | Zeigt Standard-Audiosteuerung an                                 |
| `autoplay`    | Startet automatisch beim Laden (benötigt meist `muted`)          |
| `muted`       | Startet stummgeschaltet (z. B. in Kombination mit Autoplay)      |
| `loop`        | Spielt das Audio in Endlosschleife ab                            |
| `preload`     | `none`, `metadata`, `auto` – steuert Vorladen der Datei          |
| `type`        | MIME-Type der Datei (z. B. `audio/mpeg`, `audio/ogg`)            |

---

## 🎧 Beispiel mit mehreren Formaten

```html
<audio controls preload="metadata">
  <source src="audio.ogg" type="audio/ogg" />
  <source src="audio.mp3" type="audio/mpeg" />
  <p>Ihr Browser unterstützt HTML5-Audio nicht.</p>
</audio>
```

👉 Der Browser verwendet die **erste unterstützte Quelle**.

---

## 🧠 Formatkompatibilität

| Format   | MIME-Type        | Browser-Unterstützung       |
|----------|------------------|-----------------------------|
| MP3      | `audio/mpeg`     | ✅ Alle modernen Browser     |
| Ogg Vorbis | `audio/ogg`    | ✅ Firefox, ✅ Chrome        |
| WAV      | `audio/wav`      | ✅ Große Browser, aber große Dateigröße |

---

## ♿ Barrierefreiheit

- `<audio>` hat **native Unterstützung für Tastatur und Screenreader**
- Bei wichtigen Inhalten sollten **Transkripte** bereitgestellt werden
- Verwende das `title`-Attribut, um zusätzliche Informationen zu bieten

```html
<audio controls title="Einführungspodcast Folge 1">
  <source src="intro.mp3" type="audio/mpeg" />
</audio>
```

---

## 🎨 Styling mit CSS

```css
audio {
  width: 100%;
  outline: none;
}
```

👉 Das `<audio>`-Element lässt sich nur **begrenzt stylen**. Für individuelle Player ist JavaScript nötig.

---

## 🔄 Unterschied zu `<video>`

| Element   | Medienart      | Bedienelemente | Zusätzliche Darstellung |
|-----------|----------------|----------------|--------------------------|
| `<audio>` | Nur Ton        | Ja             | Kein Bild                |
| `<video>` | Ton + Bild     | Ja             | Videoausgabe             |

---

## ❌ Häufige Fehler

| Fehler                         | Besser                                         |
|--------------------------------|------------------------------------------------|
| Nur ein Audioformat eingebunden | Immer mehrere Formate für Kompatibilität     |
| Autoplay ohne `muted`          | Wird oft blockiert – nur `muted autoplay` nutzen |
| Kein `controls`, keine Steuerung | Immer Steuerung für Nutzer:innen bereitstellen |

---

## 📚 Fazit

Das `<audio>`-Element ist die einfachste und effizienteste Methode, um **Ton in Webseiten zu integrieren** – mit optionaler Kontrolle über Wiedergabe, Lautstärke und Formatwahl.  
Barrierefreiheit, Mehrformat-Unterstützung und Performance lassen sich gut kombinieren – ideal für moderne Webanwendungen.
