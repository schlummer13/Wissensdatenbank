# `<link>` – Verknüpfung von externen Ressourcen

## 🧩 Funktion

Das `<link>`-Tag wird verwendet, um ein HTML-Dokument mit **externen Ressourcen** zu verknüpfen.  
Am häufigsten wird es genutzt, um **externe CSS-Dateien einzubinden**, aber es kann auch Icons, Fonts, Feeds oder Preloads referenzieren.

> **Hinweis:** `<link>` ist ein **self-closing Element** – es hat **kein schließendes Tag**.

---

## ✅ Grundverwendung für Stylesheets

```html
<head>
  <link rel="stylesheet" href="styles.css" />
</head>
```

**Was passiert?**  
👉 Die CSS-Datei `styles.css` wird geladen und auf das aktuelle Dokument angewendet.

---

## 🔧 Wichtige Attribute

| Attribut     | Beschreibung |
|--------------|--------------|
| `rel`        | Art der Beziehung zwischen HTML-Dokument und Ressource (z. B. `stylesheet`, `icon`, `preload`) |
| `href`       | Pfad zur externen Ressource |
| `type`       | MIME-Typ (bei Stylesheets meist `text/css`, optional) |
| `media`      | Definiert, für welches Zielmedium die Ressource gilt (z. B. `screen`, `print`, `all`) |
| `as`         | Typ der Ressource (z. B. `style`, `script`, `image`) – wichtig für `rel="preload"` |
| `crossorigin`| Für Cross-Origin Requests (z. B. bei Fonts/CDNs) |
| `integrity`  | Sicherheitsprüfung über SRI (Subresource Integrity) |

---

## 🧪 Beispiele

### 1. 🎨 Externes Stylesheet einbinden

```html
<link rel="stylesheet" href="styles/main.css" />
```

👉 Trennung von Layout (CSS) und Struktur (HTML).

---

### 2. 📄 Nur für Druckmedien

```html
<link rel="stylesheet" href="print.css" media="print" />
```

👉 Wird **nur beim Drucken** der Seite angewendet.

---

### 3. 🎯 Preload von Ressourcen

```html
<link rel="preload" href="fonts/myfont.woff2" as="font" type="font/woff2" crossorigin="anonymous" />
```

👉 Sorgt dafür, dass die Schriftart **frühzeitig geladen** wird – verbessert die Ladezeit und Darstellung.

---

### 4. 📎 Favicons einbinden

```html
<link rel="icon" href="/favicon.ico" type="image/x-icon" />
<link rel="apple-touch-icon" href="/apple-touch-icon.png" />
```

👉 Wird in der Browser-Tab-Leiste, auf Mobilgeräten oder in Bookmarks angezeigt.

---

### 5. 🌐 Web Fonts (z. B. Google Fonts)

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" />
```

👉 Lädt eine externe Schriftart für die Seite.

---

## 🔒 Sicherheit: Subresource Integrity (SRI)

```html
<link
  rel="stylesheet"
  href="https://cdn.example.com/lib.css"
  integrity="sha384-abc123..."
  crossorigin="anonymous"
/>
```

➡ Stellt sicher, dass die Ressource **nicht manipuliert** wurde – empfohlen bei externen Quellen/CDNs.

---

## 🔥 Best Practices

- Verwende `<link rel="stylesheet">` im `<head>` – Stylesheets werden **parallel zum HTML geladen**.
- Trenne Inhalte (`HTML`) von Darstellung (`CSS`) – erhöhte **Wartbarkeit** und **Wiederverwendbarkeit**.
- Nutze `media="print"` für **druckspezifisches CSS**.
- Verwende `preload` für Fonts, große Bilder oder Skripte mit hoher Priorität.
- Bei mehreren `<link>`-Tags: Sortiere nach Wichtigkeit und Medienziel.

---

## 📚 Gängige `rel`-Werte (Auswahl)

| Wert           | Zweck |
|----------------|-------|
| `stylesheet`   | Externe CSS-Datei |
| `icon`         | Favicon für Browser-Tab |
| `apple-touch-icon` | Homescreen-Icon für iOS-Geräte |
| `preload`      | Ressource vorab laden |
| `prefetch`     | Ressource vorbereitend laden für nächste Seite |
| `dns-prefetch` | DNS-Lookup für externe Domains |
| `alternate`    | Z. B. alternative Sprache oder Feed (`rel="alternate" hreflang="en"`) |

---

## ♿ Barrierefreiheit

- `<link>` selbst hat keine direkte Auswirkung auf die Barrierefreiheit.
- ABER: Die verknüpften Ressourcen (z. B. ein Kontrast-CSS) **können die Lesbarkeit stark beeinflussen**.
- CSS-Dateien sollten auf **zugängliches Design** achten: gute Farbkontraste, skalierbare Schriftgrößen, reduzierte Animationen etc.

---

## 📚 Fazit

Das `<link>`-Element ist ein **zentrales Werkzeug**, um HTML-Dokumente mit **externen Ressourcen zu verbinden** – insbesondere für Stylesheets, Icons und Performance-Optimierung.  
In modernen Webprojekten ist `<link>` ein Muss für **strukturierte, wartbare und performante Webseiten**.