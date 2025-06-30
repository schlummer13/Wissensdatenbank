# 🔒 HTTPS – Hypertext Transfer Protocol Secure

**HTTPS** ist die **sichere Version von HTTP**, dem Protokoll, über das Webseiten mit deinem Browser kommunizieren. Das "S" steht für **Secure** – also **verschlüsselte und vertrauenswürdige Datenübertragung**.

---

## 🧩 Was ist HTTPS?

HTTPS kombiniert **HTTP** mit **SSL/TLS-Verschlüsselung** (Secure Sockets Layer / Transport Layer Security).  
Es sorgt dafür, dass Daten **verschlüsselt**, **authentifiziert** und **vor Manipulation geschützt** übertragen werden.

➡️ Ohne HTTPS kann jede Anfrage im Klartext mitgelesen oder verändert werden – z. B. von Angreifern im WLAN, Internetanbietern oder Proxy-Servern.

---

## 🔐 Warum ist HTTPS wichtig?

| Vorteil                    | Erklärung                                                                 |
|----------------------------|---------------------------------------------------------------------------|
| 🔒 **Verschlüsselung**      | Niemand kann Daten unterwegs einsehen (z. B. Passwörter, Formulare, etc.) |
| ✅ **Authentifizierung**    | Sicherheit, dass man mit dem „echten“ Server spricht                      |
| 🛡 **Integrität**           | Schutz vor Manipulation unterwegs                                         |
| 🌍 **Vertrauenswürdigkeit** | Moderne Browser zeigen Warnungen bei HTTP-Seiten                         |
| 📈 **SEO-Vorteil**          | Google bevorzugt HTTPS-Webseiten im Ranking                              |

---

## 🔧 Wie funktioniert HTTPS?

1. **Verbindungsaufbau (Handshake):**

   - Browser stellt Verbindung zum Server her
   - Server sendet ein **SSL-Zertifikat**
   - Browser prüft: Ist das Zertifikat gültig?
   - Danach wird ein **Schlüssel für die Verschlüsselung** ausgetauscht

2. **Datenübertragung:**

   - Alle folgenden Daten sind verschlüsselt
   - Selbst bei „Man-in-the-Middle“-Angriffen können Inhalte nicht gelesen werden

---

## 📜 Was ist ein SSL-/TLS-Zertifikat?

Ein Zertifikat:

- bestätigt die **Identität** des Servers (Domain)
- enthält einen **öffentlichen Schlüssel**
- wird von einer **Zertifizierungsstelle (CA)** ausgestellt (z. B. Let's Encrypt, DigiCert)

### Aufbau:

```text
Zertifikat für: www.example.com
Ausgestellt von: Let's Encrypt
Gültig bis: 20.12.2025
Schlüssel: (RSA/ECDSA Public Key)
```

---

## 🧪 HTTPS in der Praxis

- URL beginnt mit `https://`
- 🔒 Symbol in der Adresszeile
- Auf Mobilgeräten meist durch ein Schloss-Symbol erkennbar

---

## 🚧 HTTP vs. HTTPS

| Eigenschaft       | HTTP                           | HTTPS                                |
|-------------------|--------------------------------|---------------------------------------|
| Verschlüsselung   | ❌ Nein                        | ✅ Ja                                  |
| Daten sichtbar?   | ✅ Ja – Klartext               | ❌ Nein – nur der Server kann lesen    |
| Sicherheit        | ❌ Unsicher                    | ✅ Sicher                              |
| Verwendung        | Veraltet                      | Standard seit Jahren                  |
| Browser-Warnung   | ❌ Keine (früher)              | ⚠️ Warnung bei fehlendem HTTPS        |

---

## 📦 HTTPS einrichten (Beispiel: mit Let's Encrypt)

### 1. SSL-Zertifikat kostenlos anfordern:

```bash
sudo certbot --nginx -d example.com
```

### 2. NGINX-Konfiguration anpassen:

```nginx
server {
  listen 443 ssl;
  ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
  ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;

  location / {
    proxy_pass http://localhost:3000;
  }
}
```

### 3. Automatische Verlängerung aktivieren:

```bash
sudo certbot renew --dry-run
```

---

## 🔐 HTTPS in Webentwicklung & APIs

- **Fetch / AJAX / REST APIs**: sollten **immer HTTPS** nutzen
- **Cookies mit `Secure`-Attribut** werden nur per HTTPS übertragen
- `SameSite=None` Cookies **müssen** `Secure` sein!
- Bei Login-Formularen oder Zahlungsdaten: HTTPS ist **Pflicht**

---

## ❗ Typische HTTPS-Fehler

| Problem                          | Lösung                                                        |
|----------------------------------|---------------------------------------------------------------|
| ❌ Zertifikat abgelaufen         | Zertifikat neu generieren                                     |
| ⚠️ Zertifikat nicht vertrauenswürdig | Nur Zertifikate von offiziellen CAs nutzen                   |
| 🔁 Mixed Content (Bilder, JS via HTTP) | Alle Ressourcen per HTTPS einbinden                         |
| 🔁 Weiterleitung fehlt           | Weiterleitung von HTTP → HTTPS einrichten (301-Redirect)      |

---

## 📘 Fazit

HTTPS ist heute **unverzichtbar**:

- Für **Vertrauen**, **Sicherheit**, **Datenschutz**
- **Pflicht für Login-Seiten, Formulare und APIs**
- Wird von Browsern, Google & Nutzern **erwartet**

> 💡 HTTPS sollte **standardmäßig aktiv** sein – und nicht als „Zusatz“ behandelt werden!

---

## 🔗 Weiterführende Links

- [Let’s Encrypt](https://letsencrypt.org/)
- [Mozilla TLS-Konfig-Generator](https://ssl-config.mozilla.org/)
- [Google HTTPS Guidelines](https://web.dev/https/)