# 🔐 Content Security Policy (CSP) – Schutz vor XSS & Co.

## 🧩 Was ist CSP?

**Content Security Policy (CSP)** ist eine Sicherheitsfunktion, mit der du festlegen kannst, **welche Inhalte (Skripte, Styles, Bilder usw.) auf deiner Webseite erlaubt sind**.  
Ziel ist es, **Cross-Site Scripting (XSS)**, **Code Injection**, **Clickjacking** und andere Angriffe zu verhindern.

CSP wird in der Regel **per HTTP-Header** gesetzt, kann aber auch über ein `<meta>`-Tag eingebunden werden (nicht empfohlen für vollständige Richtlinien).

---

## ✅ Beispiel: Einfache CSP über HTTP-Header

```http
Content-Security-Policy: default-src 'self'
```

➡ Bedeutet: Nur Ressourcen vom gleichen Ursprung (Domain) dürfen geladen werden.

---

## 🔧 Einbindung per HTML `<meta>`-Tag (nur Basisrichtlinien)

```html
<meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self'" />
```

⚠️ **Achtung:** Nicht alle CSP-Funktionen sind über `<meta>` verfügbar – **HTTP-Header wird empfohlen**.

---

## 📚 Die wichtigsten Direktiven

| Direktive         | Bedeutung |
|-------------------|-----------|
| `default-src`     | Standard-Quelle für alle Ressourcen |
| `script-src`      | Für JavaScript-Dateien und Inline-Skripte |
| `style-src`       | Für CSS-Dateien und Inline-Styles |
| `img-src`         | Für Bilder |
| `font-src`        | Für Schriftarten |
| `connect-src`     | Für XHR, Fetch, WebSockets |
| `media-src`       | Für Video/Audio-Dateien |
| `frame-src`       | Für `<iframe>`-Inhalte |
| `object-src`      | Für `<object>`, `<embed>`, `<applet>` |
| `base-uri`        | Für das `<base>`-Tag |
| `form-action`     | Wo Formulare abgeschickt werden dürfen |
| `frame-ancestors` | Wer die Seite per `<iframe>` einbetten darf |
| `report-uri`      | URL für CSP-Verletzungsberichte (deprecated) |
| `report-to`       | Neuere Methode für Reporting-API |

---

## 🧪 Praxisbeispiele

### 1. 🔐 Nur eigene Ressourcen erlauben

```http
Content-Security-Policy: default-src 'self'
```

➡ Keine externen Skripte, Fonts, Styles erlaubt.

---

### 2. 🌐 Bestimmte Domains erlauben

```http
Content-Security-Policy: 
  default-src 'self';
  img-src 'self' https://cdn.example.com;
  script-src 'self' https://apis.example.com;
```

➡ Skripte und Bilder dürfen zusätzlich von definierten Domains geladen werden.

---

### 3. 🔄 Dynamisches Laden mit `unsafe-inline` / `unsafe-eval` (⚠️ vermeiden!)

```http
Content-Security-Policy: 
  script-src 'self' 'unsafe-inline';
```

⚠️ Verwendet **unsichere Inline-Skripte** – nur im Notfall einsetzen, z. B. bei alten Projekten.

---

### 4. 📣 CSP mit Berichtsfunktion

```http
Content-Security-Policy: 
  default-src 'self';
  report-uri /csp-violation-report
```

➡ Wenn Verstöße auftreten, werden JSON-Berichte an den Server gesendet.  
*Alternative für moderne Browser: `report-to` verwenden.*

---

## 🧠 Tipps für sicheres Setup

- **Kein `unsafe-inline` oder `unsafe-eval` verwenden** – außer du weißt genau, was du tust.
- Nutze **Nonces oder Hashes**, um gezielt einzelne Inline-Skripte freizugeben.
- Starte mit **CSP in "Report-Only" Modus**, um Verstöße zu protokollieren, ohne Inhalte zu blockieren.

### Beispiel: Report-Only

```http
Content-Security-Policy-Report-Only: default-src 'self'; report-uri /csp-report
```

---

## 🔐 Verwendung von Nonces (empfohlen)

```html
<script nonce="abc123">console.log("Sicherer Inline-Script");</script>
```

```http
Content-Security-Policy: script-src 'nonce-abc123'
```

➡ Nur das Inline-Script mit dem passenden `nonce` darf ausgeführt werden.

---

## 🛠 Tools & Validierung

- [CSP Evaluator (Google)](https://csp-evaluator.withgoogle.com/)
- [Mozilla CSP Guide](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)
- [Report URI](https://report-uri.com/) – Visualisierung von CSP-Verstößen

---

## 📚 Fazit

CSP ist ein **leistungsstarkes Werkzeug**, um deine Website vor häufigen Web-Angriffen zu schützen. Richtig eingesetzt, verhindert es das Nachladen unerwünschter Inhalte und das Ausführen von schädlichem JavaScript.

Es lohnt sich, etwas Zeit in die Konfiguration zu investieren – gerade bei modernen Webanwendungen und öffentlichen Plattformen.
