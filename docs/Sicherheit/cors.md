# 🌐 CORS – Cross-Origin Resource Sharing

**CORS** ist ein Sicherheitsmechanismus im Web, der kontrolliert, ob und wie Inhalte **zwischen unterschiedlichen Ursprüngen (Domains)** ausgetauscht werden dürfen.

---

## 🧩 Was ist ein „Origin“?

Ein **Origin** besteht aus:

- **Protokoll** (`http`, `https`)
- **Domain** (`example.com`)
- **Port** (`:80`, `:443`, etc.)

👉 Zwei Seiten mit unterschiedlichen Origins:

```text
https://example.com       ≠     http://example.com
https://api.example.com   ≠     https://example.com
```

---

## 🚫 Was blockiert CORS?

Standardmäßig verbietet der **Browser** Webanwendungen, Anfragen an einen anderen Origin zu senden (z. B. von `meineseite.de` zu `api.fremddomain.de`), **außer** der Zielserver erlaubt das explizit.

> Dies schützt den Benutzer vor **Cross-Site-Scripting-Angriffen (XSS)** und **Session Hijacking**.

---

## ✅ Wie funktioniert CORS?

CORS funktioniert über HTTP-Header. Wenn eine Webseite eine **cross-origin-Anfrage** stellt (z. B. per `fetch()`), dann prüft der Browser:

1. **Was sagt der Zielserver?**
2. Gibt es den Header:

```http
Access-Control-Allow-Origin: https://meineseite.de
```

3. Wenn ja → Anfrage erlaubt  
   Wenn nein → Anfrage geblockt durch den Browser

---

## 🔧 Beispiel: Erlaubte Anfrage

```http
GET /daten
Host: api.example.com
Origin: https://meineseite.de
```

Antwort:

```http
Access-Control-Allow-Origin: https://meineseite.de
```

➡️ Der Browser lässt die Antwort durch.

---

## ❌ Beispiel: Geblockte Anfrage

Wenn der Zielserver **diesen Header nicht zurückgibt**, blockiert der Browser die Antwort – auch wenn die Anfrage technisch gesendet wurde.

---

## 🔄 Preflight-Anfrage (OPTIONS)

Bei „komplizierten“ Anfragen (z. B. `PUT`, `DELETE`, oder eigene Header) schickt der Browser **vorher** eine **OPTIONS-Anfrage**:

```http
OPTIONS /api/benutzer
Origin: https://app.meinefirma.de
Access-Control-Request-Method: PUT
Access-Control-Request-Headers: Content-Type
```

➡️ Erst wenn der Server darauf antwortet mit:

```http
Access-Control-Allow-Origin: https://app.meinefirma.de
Access-Control-Allow-Methods: PUT
Access-Control-Allow-Headers: Content-Type
```

…wird die eigentliche Anfrage ausgeführt.

---

## 📦 Wichtige CORS-Header

| Header                        | Bedeutung                                                  |
|-------------------------------|-------------------------------------------------------------|
| `Access-Control-Allow-Origin` | Wer darf zugreifen? (`*` = alle)                          |
| `Access-Control-Allow-Methods`| Welche Methoden sind erlaubt? (`GET`, `POST`, `PUT`, ...) |
| `Access-Control-Allow-Headers`| Welche Header dürfen gesendet werden?                    |
| `Access-Control-Allow-Credentials` | Dürfen Cookies/Mitglieder-Infos gesendet werden?    |
| `Access-Control-Expose-Headers`   | Welche Response-Header dürfen sichtbar sein?         |

---

## ⚙️ `fetch()` mit CORS

### Einfache Anfrage:

```js
fetch("https://api.fremdseite.de/daten")
  .then(res => res.json())
  .then(data => console.log(data));
```

### Mit Credentials (Cookies etc.):

```js
fetch("https://api.fremdseite.de/daten", {
  credentials: "include"
});
```

➡️ Server muss dann auch `Access-Control-Allow-Credentials: true` setzen.

---

## 🛠 Tipps zur Konfiguration

### ✅ Server muss aktiv CORS erlauben:

#### Node.js (Express):

```js
const cors = require('cors');
app.use(cors({ origin: "https://meineseite.de" }));
```

#### PHP:

```php
header("Access-Control-Allow-Origin: https://meineseite.de");
```

#### Apache (`.htaccess`):

```apache
Header set Access-Control-Allow-Origin "*"
```

---

## 🔐 Sicherheitshinweis

- Niemals einfach `Access-Control-Allow-Origin: *` UND `credentials: true` kombinieren!
- Öffne deine API nur gezielt für vertrauenswürdige Domains.
- CORS schützt **nur den Browser-Nutzer**, **nicht den Server!**

---

## ✅ Zusammenfassung

| Thema             | Erklärung                                                |
|-------------------|----------------------------------------------------------|
| CORS              | Kontrolliert Zugriff zwischen Domains                    |
| Origin            | Kombination aus Protokoll, Domain, Port                  |
| Warum?            | Schutz vor unerlaubtem Zugriff / Cross-Origin-Hacking   |
| Wer muss handeln? | Immer der **Server** – nicht der Client!                |
| Was ist nötig?    | Korrekte HTTP-Header (`Access-Control-*`)               |

---

> 📘 Tipp: CORS-Fehler erscheinen nur **im Browser** – in Tools wie Postman funktioniert alles trotzdem!