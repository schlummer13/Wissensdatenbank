# `<meta>` – Metadaten für HTML-Dokumente

## 🧩 Funktion

Das `<meta>`-Element wird im `<head>` einer HTML-Seite verwendet, um **Metadaten** bereitzustellen – also **Informationen über die Seite**, nicht für die Darstellung der Inhalte selbst.  
Meta-Tags werden von **Suchmaschinen, Browsern, Social Media-Plattformen und Diensten** wie Screenreadern ausgewertet.

> 📌 `<meta>` ist ein **self-closing Element** (kein öffnendes und schließendes Tag-Paar).

---

## ✅ Grundstruktur

```html
<meta name="description" content="Dies ist eine Beispielseite über HTML-Meta-Tags." />
```

---

## 🔧 Wichtige Attribute

| Attribut   | Beschreibung |
|------------|--------------|
| `name`     | Gibt den Namen des Metadateninhalts an (z. B. `description`, `viewport`) |
| `content`  | Der eigentliche Inhalt der Metadaten |
| `http-equiv` | Simuliert HTTP-Header (z. B. `refresh`, `content-type`) |
| `charset`  | Zeichencodierung (z. B. UTF-8) – Sonderform, hat kein `content` |

---

## 📚 Typische Arten von `<meta>`-Tags

---

### 🔤 1. Zeichencodierung

```html
<meta charset="UTF-8" />
```

👉 **Pflichtangabe** in modernen Webseiten, legt die Zeichencodierung fest (z. B. für Umlaute, Emojis etc.).

---

### 🌐 2. Viewport (Responsive Design)

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

👉 Sorgt dafür, dass die Seite auf Mobilgeräten korrekt dargestellt wird.  
Essentiell für **responsive Webseiten**.

---

### 📝 3. Beschreibung (SEO)

```html
<meta name="description" content="Lerne alles über HTML-Meta-Tags, SEO, Sicherheit und mehr." />
```

👉 Wird in den **Suchergebnissen von Google** als Seitenbeschreibung angezeigt.

---

### 🔑 4. Schlüsselwörter (veraltet für SEO)

```html
<meta name="keywords" content="html, meta, seo, webentwicklung" />
```

👉 Wird von **modernen Suchmaschinen ignoriert** – früher relevant.

---

### 📣 5. Autor & Copyright

```html
<meta name="author" content="Florian Fenzl" />
<meta name="copyright" content="© 2025 solago GmbH" />
```

---

### 🔁 6. Seiten-Refresh / Weiterleitung

```html
<meta http-equiv="refresh" content="5; url=https://example.com" />
```

👉 Leitet nach 5 Sekunden automatisch weiter – sollte mit Vorsicht verwendet werden.

---

### 🌍 7. Content-Type (veraltet)

```html
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
```

👉 Wird durch `charset` ersetzt – nur noch in Altprojekten notwendig.

---

### 🔒 8. Sicherheit (z. B. Content Security Policy)

```html
<meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' https://apis.example.com" />
```

👉 Schränkt Ressourcen ein, schützt vor Cross-Site Scripting (XSS).  
**Wird meist serverseitig via HTTP-Header gesetzt**, nicht im HTML.

---

## 💬 Meta-Tags für Social Media (Open Graph, Twitter Cards)

### 🟦 Open Graph (Facebook, LinkedIn, etc.)

```html
<meta property="og:title" content="Meine Seite" />
<meta property="og:description" content="Beschreibung für Social Media" />
<meta property="og:image" content="https://example.com/vorschau.jpg" />
<meta property="og:url" content="https://example.com" />
```

### 🐦 Twitter Cards

```html
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Seitentitel" />
<meta name="twitter:description" content="Kurze Beschreibung" />
<meta name="twitter:image" content="https://example.com/preview.jpg" />
```

👉 Sorgt für **hübsche Vorschauen** beim Teilen auf sozialen Netzwerken.

---

## 🔍 Best Practices

- **Immer `charset="UTF-8"` verwenden** – am besten als erstes Element im `<head>`.
- Nutze `viewport`, damit deine Seite auf Mobilgeräten funktioniert.
- Verwende eine **klare und prägnante `description`** – idealerweise 150–160 Zeichen.
- Vermeide veraltete Tags wie `keywords`, `expires`, `generator`.
- Für professionelle Seiten: ergänze Social Media Tags (`og:`, `twitter:`) & Sicherheitsrichtlinien (`Content-Security-Policy`).

---

## ♿ Barrierefreiheit

- Meta-Tags wie `viewport` und `charset` wirken sich **indirekt positiv** auf die Barrierefreiheit aus.
- Für Screenreader sind Meta-Tags selbst nicht relevant, aber sie helfen bei der **technischen Konsistenz** der Seite.

---

## 📚 Fazit

Meta-Tags gehören zu den unsichtbaren, aber **entscheidenden Bausteinen jeder Webseite**.  
Sie steuern, **wie deine Seite gelesen, dargestellt, interpretiert und geteilt** wird – von Suchmaschinen, Browsern, Social Media-Plattformen und technischen Tools.
