# `<embed>` – Externe Inhalte einbetten

## 🧩 Funktion

Das `<embed>`-Element wird verwendet, um **externe Inhalte direkt in eine HTML-Seite einzubetten**. Dazu zählen unter anderem:

- PDF-Dateien
- Videos (z. B. MP4, SWF)
- Audio-Dateien
- HTML-Anwendungen
- animierte SVGs oder interaktive Tools

> 📌 Im Gegensatz zu `<iframe>` oder `<object>` ist `<embed>` ein **self-closing Tag**, der direkt eingebettete Medien oder Plugins rendert – **ohne strukturiertes HTML-Innenleben**.

---

## ✅ Grundverwendung

```html
<embed src="dokument.pdf" type="application/pdf" width="800" height="600" />
```

- `src` legt die eingebundene Datei fest
- `type` spezifiziert den MIME-Type (z. B. `application/pdf`)
- `width` und `height` bestimmen die Darstellungsgröße im Dokument

---

## 🔧 Attribute im Überblick

| Attribut   | Beschreibung                                                     |
|------------|------------------------------------------------------------------|
| `src`      | URL oder Pfad zur einzubettenden Datei                           |
| `type`     | MIME-Type des Inhalts (z. B. `video/mp4`, `application/pdf`)     |
| `width`    | Breite des eingebetteten Inhalts (z. B. `100%` oder `640`)       |
| `height`   | Höhe des eingebetteten Inhalts                                   |
| `title`    | (Optional) Beschreibung für Barrierefreiheit & Tooltip           |
| `pluginspage` | (veraltet) URL zur Plugin-Downloadseite – heute irrelevant    |

---

## 📄 Beispiel: PDF-Dokument anzeigen

```html
<embed src="/downloads/handbuch.pdf" type="application/pdf" width="100%" height="600px" />
```

👉 Wird direkt im Browser angezeigt (sofern der Browser PDF-Rendering unterstützt).

---

## 🎞 Beispiel: Video (MP4)

```html
<embed src="video.mp4" type="video/mp4" width="800" height="450" />
```

> ⚠️ Für Medien wie Video und Audio sind `<video>` bzw. `<audio>` **semantisch und funktional besser geeignet**.

---

## 🖼 Unterschied zu `<object>` und `<iframe>`

| Merkmal            | `<embed>`                  | `<object>`                 | `<iframe>`                  |
|--------------------|----------------------------|----------------------------|-----------------------------|
| Selbstschließend   | ✅ Ja                      | ❌ Nein                    | ❌ Nein                     |
| Inhalt fallbackbar | ❌ Nein                    | ✅ Ja (Inhalt möglich)     | ✅ Ja (Inhalt möglich)      |
| Sandbox fähig      | ❌ Nein                    | ❌ Eingeschränkt           | ✅ Ja (`sandbox` verfügbar) |
| MIME-Type wichtig  | ✅ Ja                      | ✅ Ja                      | 🔄 Nur für Content-Typ-Prüfung |

---

## ♿ Barrierefreiheit

- Verwende das `title`-Attribut für Screenreader und Tooltip-Infos
- `<embed>`-Inhalte **haben keine semantische Bedeutung**
- Für interaktive oder relevante Inhalte ggf. auf `<iframe>` oder `<object>` umsteigen

```html
<embed src="karte.svg" type="image/svg+xml" width="500" height="400" title="Interaktive Karte von Berlin" />
```

---

## ❌ Häufige Fehler

| Fehler                              | Besser                                          |
|-------------------------------------|-------------------------------------------------|
| Kein MIME-Type angegeben            | Immer `type` setzen                             |
| Für HTML-/JS-Apps verwendet         | Lieber `<iframe>` verwenden                    |
| Kein Fallback für nicht unterstützte Inhalte | Nutze `<object>` für Backup-Inhalte         |

---

## 🧠 Wann ist `<embed>` sinnvoll?

| Szenario                     | Empfehlung     |
|------------------------------|----------------|
| PDF-Dokument direkt anzeigen | ✅ Ja          |
| Nur eine Datei mit sicherem MIME-Type | ✅ Ja    |
| Mehrere Inhaltsalternativen oder Fallback nötig | ❌ Besser `<object>` |
| Strukturierte Inhalte oder Webanwendung | ❌ Besser `<iframe>`     |

---

## 📚 Fazit

`<embed>` ist ein **praktisches und leichtgewichtiges Element**, um Medien oder Inhalte wie PDF, Videos oder SVGs direkt anzuzeigen.  
Für einfache Einbettungen genügt es vollkommen – bei komplexeren oder interaktiven Inhalten sind `<iframe>` oder `<object>` oft besser geeignet.

> 💬 Als Nächstes: Möchtest du mit `<object>`, `<canvas>`, `<svg>` oder interaktiven Webelementen weitermachen?