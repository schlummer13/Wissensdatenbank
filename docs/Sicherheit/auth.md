# 🔐 Authentifizierung (Auth)

Authentifizierung ist ein zentraler Bestandteil der IT-Sicherheit. Sie stellt sicher, dass eine Person oder ein System **wirklich derjenige ist, der er vorgibt zu sein**.

---

## 🧩 Was ist Authentifizierung?

> **Authentifizierung (Auth)** ist der Prozess, bei dem die Identität eines Benutzers, Geräts oder Systems überprüft wird – in der Regel **vor dem Zugriff auf geschützte Ressourcen**.

Sie beantwortet die Frage:  
➡️ **"Wer bist du – und kannst du das beweisen?"**

---

## 📘 Authentifizierung vs. Autorisierung

| Begriff           | Bedeutung                                    |
|-------------------|-----------------------------------------------|
| **Authentifizierung** | Wer bist du? (Identitätsprüfung)           |
| **Autorisierung**      | Was darfst du? (Zugriffsrechte nach Login) |

---

## 🔑 Klassische Authentifizierungsfaktoren

Die Sicherheit steigt mit der Anzahl kombinierter Faktoren. Man spricht von **"Multi-Faktor-Authentifizierung (MFA)"**.

| Faktor-Typ            | Beispiel                                 |
|------------------------|------------------------------------------|
| **Wissen (Etwas, das man weiß)**   | Passwort, PIN                      |
| **Besitz (Etwas, das man hat)**    | Smartphone, Token, Karte          |
| **Sein (Etwas, das man ist)**      | Fingerabdruck, Gesicht, Iris      |
| **Ort (Wo man ist)**               | Standortdaten                     |
| **Zeit (Wann man ist)**            | Zeitfenster-basiert (z. B. TANs)  |

---

## 🛠️ Authentifizierungsmethoden im Web

### 1. 🔒 **Passwortbasierte Auth**

- Klassischster Ansatz: Benutzername + Passwort
- Sicherheitsrisiko bei:
  - Wiederverwendung
  - Einfachen Passwörtern
  - Kein Rate-Limit

✅ Verstärken durch:
- Hashing (z. B. bcrypt)
- Salting
- MFA

---

### 2. 🔑 **Token-basierte Auth**

- Moderne Methode bei Web-APIs
- Server gibt nach Login ein **Token** zurück (z. B. JWT)
- Dieses Token wird bei jedem weiteren Request mitgeschickt

Vorteile:
- Kein Session-Tracking notwendig
- Skalierbar, mobilfreundlich

```http
GET /api/user
Authorization: Bearer eyJhbGciOiJIUzI1NiIs...
```

---

### 3. 🧩 **OAuth 2.0 / OpenID Connect**

- **Delegierte Authentifizierung**
- Ermöglicht Login über Drittanbieter (Google, GitHub, Facebook)
- Token-System mit Rollen und Gültigkeit

➡️ Benutzer gibt Login nicht direkt auf deiner Seite ein

---

### 4. 📱 **Zwei-Faktor-Authentifizierung (2FA)**

- Kombiniert Passwort mit zusätzlichem Faktor
  - Einmalpasswort (OTP via App oder SMS)
  - YubiKey oder ähnliches Hardware-Token

Erhöht Sicherheit drastisch!

---

## 🧪 Authentifizierung in der Praxis

| Einsatzgebiet        | Typische Methode                         |
|----------------------|-------------------------------------------|
| Web-Anwendungen      | Passwort, Token, OAuth                   |
| Unternehmensnetzwerke| Smartcards, AD-Login                     |
| Mobile Apps          | Biometrie, Token, OAuth                  |
| APIs                 | API Key, JWT, HMAC, OAuth                |

---

## ⚠️ Risiken bei Authentifizierung

- **Phishing** – gestohlene Login-Daten
- **Brute-Force** – automatisches Ausprobieren
- **Credential Stuffing** – Wiederverwendung gehackter Daten
- **Man-in-the-Middle** – Abhören unverschlüsselter Kommunikation

✅ Maßnahmen:
- HTTPS überall
- Rate-Limiting
- MFA
- Session-Timeouts
- Passwort-Richtlinien
- Device Binding

---

## 🔐 Passwort-Management-Tipps

- Verwende **lange**, zufällige Passwörter (mind. 12 Zeichen)
- Nutze einen **Passwortmanager**
- Ändere Passwörter bei **Datenlecks**
- **Kein Wiederverwenden** von Passwörtern

---

## 🧠 Zusammenfassung

| Thema                        | Wichtigster Punkt                                 |
|------------------------------|----------------------------------------------------|
| Ziel der Authentifizierung   | Nachweis der Identität                            |
| Sichere Methoden             | MFA, Token, OAuth                                 |
| Risiken                      | Phishing, Datenlecks, schwache Passwörter         |
| Schutzmaßnahmen              | HTTPS, Passwortmanager, 2FA, Session-Management   |
