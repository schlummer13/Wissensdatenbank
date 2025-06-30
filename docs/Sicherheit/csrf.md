# 🛡️ CSRF – Cross-Site Request Forgery

**CSRF** (deutsch: Website-übergreifende Anfragenfälschung) ist eine **Sicherheitslücke**, bei der ein Angreifer eine **unbefugte Aktion im Namen eines eingeloggten Nutzers** auf einer vertrauenswürdigen Webseite auslöst.

---

## 🧩 Was passiert bei einem CSRF-Angriff?

1. Ein Benutzer ist z. B. bei `meinebank.de` eingeloggt.
2. Der Angreifer bringt ihn dazu, unbemerkt eine Anfrage an `meinebank.de` auszulösen – z. B. durch ein <img>-Tag, Formular oder JavaScript.
3. Die Anfrage enthält **gültige Cookies oder Tokens**, weil der Browser diese automatisch mitsendet.
4. Die Bank führt die Aktion aus, **ohne zu wissen**, dass sie vom Angreifer stammt.

---

## ⚠️ Beispiel: Kontostand manipulieren

```html
<!-- In einem schädlichen Blogartikel eingebaut: -->
<img src="https://meinebank.de/ueberweisung?betrag=1000&ziel=angreifer" />
```

Wenn der Nutzer bei `meinebank.de` eingeloggt ist, könnte das Geld überwiesen werden, **ohne dass er etwas merkt**!

---

## 🛠️ Wie verhindert man CSRF?

### ✅ 1. **CSRF-Tokens (Synchronizer Token Pattern)**

- Server generiert einen **zufälligen, eindeutigen Token**
- Token wird mit jeder Anfrage (z. B. POST-Formular) mitgeschickt
- Server prüft: ist der Token gültig?

```html
<form action="/profil" method="post">
  <input type="hidden" name="csrf_token" value="xyz123abc" />
  <input type="text" name="name" />
  <button type="submit">Speichern</button>
</form>
```

➡️ Token muss bei jeder Sitzung neu erzeugt werden.

---

### ✅ 2. **SameSite-Cookies**

```http
Set-Cookie: sessionid=abc123; SameSite=Strict
```

- **`SameSite=Strict`**: Cookie wird **nicht** bei Cross-Site-Requests gesendet
- **`SameSite=Lax`**: Nur bei einfachen GETs gesendet
- **`SameSite=None`**: Nur mit `Secure`, wird bei allen Anfragen gesendet

➡️ Browserseitige Verteidigung – sehr effektiv bei modernen Browsern.

---

### ✅ 3. **Vermeide zustandsverändernde GET-Anfragen**

- Verwende **nur POST, PUT oder DELETE** für Aktionen wie:
  - Einstellungen ändern
  - Daten löschen
  - Überweisungen durchführen

---

### ✅ 4. **Token in HTTP-Header statt in Cookies**

- Bei APIs: Authentifizierung via Header (`Authorization`) statt via Cookie
- So werden keine sensiblen Daten automatisch vom Browser mitgesendet

---

## 🧪 Sicherheitsprinzip: Origin & Referer prüfen

Ein Server kann den **`Origin`** oder **`Referer`** Header prüfen:

```http
Origin: https://meineseite.de
```

➡️ Stimmt dieser nicht mit der erwarteten Domain überein, wird die Anfrage abgelehnt.

---

## ❌ Was schützt **nicht** gegen CSRF?

| Maßnahme         | Warum nicht sicher?                                      |
|------------------|-----------------------------------------------------------|
| CAPTCHA          | Hält Bots auf – nicht echte Benutzer mit gültigen Cookies |
| Session-Cookies  | Werden automatisch gesendet – das ist das Problem         |
| Nur POST-Methoden | CSRF funktioniert auch mit POST (nicht GET ist besser!)  |
| CORS             | Schützt nur Inhalte, **nicht Aktionen** per POST          |

---

## ✅ Zusammenfassung

| Thema                 | Erklärung                                               |
|------------------------|---------------------------------------------------------|
| Was ist CSRF?         | Fremde Seite zwingt Nutzer zu unerwünschter Aktion      |
| Wie funktioniert es?  | Automatische Cookie-Weitergabe bei eingeloggten Nutzern |
| Schutzmaßnahmen       | CSRF-Tokens, SameSite-Cookies, Header-Prüfung           |
| Gute Praxis           | Immer serverseitige Validierung implementieren          |

---

> 🔐 Moderne Frameworks (z. B. Django, Laravel, Spring) haben CSRF-Schutz bereits integriert – **aber nur, wenn richtig genutzt!**

📘 Siehe auch: [OWASP CSRF Guide](https://owasp.org/www-community/attacks/csrf)