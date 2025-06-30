# ⚠️ XSS – Cross-Site Scripting

**XSS (Cross-Site Scripting)** ist eine der **häufigsten Sicherheitslücken** im Web. Dabei gelingt es Angreifern, **schädlichen JavaScript-Code in eine Webseite einzuschleusen**, der dann im Browser anderer Nutzer ausgeführt wird.

---

## 🧩 Was ist das Ziel eines XSS-Angriffs?

- Zugriff auf **Cookies**, **Session-Daten** oder **Tokens**
- **Phishing-Formulare** einfügen
- **Benutzereingaben manipulieren**
- JavaScript-Befehle im Kontext des Opfers ausführen
- Weiterleitung zu **gefälschten Webseiten**

---

## 🧪 Einfaches Beispiel

Angreifer speichert folgenden Code in einem Eingabefeld:

```html
<script>alert('XSS-Angriff!');</script>
```

Wenn dieser Code **ungefiltert** auf einer Webseite angezeigt wird, führt der Browser ihn aus – **als wäre es legitimer Code** der Seite.

---

## 🚨 Arten von XSS

### 1. **Stored XSS (Gespeichert)**

- Schädlicher Code wird **permanenter Teil** der Webseite (z. B. durch Kommentare, Profile, Nachrichten)
- Jeder Nutzer sieht den eingeschleusten Code

👉 **Am gefährlichsten!**

---

### 2. **Reflected XSS (Zurückgespiegelt)**

- Angriffscode wird **per URL** eingeschleust und **direkt in die Antwort eingebaut**
- Benutzer wird z. B. durch Link oder E-Mail dazu verleitet, die URL aufzurufen

**Beispiel-URL:**

```
https://example.com/suche?q=<script>alert('XSS')</script>
```

---

### 3. **DOM-Based XSS**

- XSS entsteht **ausschließlich im JavaScript im Browser** (nicht im Server-HTML)
- JavaScript verwendet unsichere Datenquellen wie `location.hash` oder `document.referrer`

**Beispiel:**

```js
document.body.innerHTML = location.hash;
```

Aufruf:

```
https://example.com/#<script>alert('XSS')</script>
```

---

## 🔧 Schutzmaßnahmen gegen XSS

### ✅ 1. **HTML escapen**

- Wandelt Sonderzeichen wie `<`, `>`, `"`, `'` in HTML-Entities um:

| Zeichen | Escaped |
|---------|---------|
| `<`     | `&lt;`  |
| `>`     | `&gt;`  |
| `"`     | `&quot;`|
| `'`     | `&#x27;`|

➡️ Nie direkt Benutzereingaben in HTML einfügen ohne Escaping!

---

### ✅ 2. **Content Security Policy (CSP)**

- Verhindert inline-Skripte und blockiert schadhafte Domains

```http
Content-Security-Policy: default-src 'self';
```

➡️ Browser blockiert JavaScript von nicht autorisierten Quellen

---

### ✅ 3. **Keine `innerHTML`, nur `textContent`**

```js
// ❌ Unsicher
element.innerHTML = userInput;

// ✅ Sicher
element.textContent = userInput;
```

---

### ✅ 4. **Eingabefilterung & Whitelisting**

- Eingaben nur erlauben, wenn sie bestimmten Formaten entsprechen (z. B. nur Buchstaben)
- Blacklisting ist unsicher! Angreifer finden Umgehungsmöglichkeiten

---

### ✅ 5. **Frameworks richtig nutzen**

Frameworks wie React, Vue oder Angular:

- Escapen automatisch Inhalte
- Verwenden virtuelle DOMs
- ✨ Achtung: Direktives HTML (`v-html`, `dangerouslySetInnerHTML`) ist **gefährlich**!

---

## ❌ Was schützt **nicht** gegen XSS?

| Methode               | Warum nicht ausreichend?                         |
|------------------------|--------------------------------------------------|
| HTTPS                 | Schützt nur Übertragung, nicht Inhalt             |
| Server-Schutz (z. B. .htaccess) | Schützt nicht vor clientseitiger Ausführung |
| Nur POST verwenden     | XSS kann auch über POST eingeschleust werden     |

---

## 🧪 Beispiel für sicheren Umgang

```html
<!-- Unsicher -->
<div id="ausgabe"></div>

<script>
  const userInput = "<script>alert('XSS')</script>";
  document.getElementById("ausgabe").innerHTML = userInput; // ❌
</script>
```

```html
<!-- Sicher -->
<div id="ausgabe"></div>

<script>
  const userInput = "<script>alert('XSS')</script>";
  document.getElementById("ausgabe").textContent = userInput; // ✅
</script>
```

---

## 📘 Fazit

| Thema             | Erklärung                                               |
|--------------------|---------------------------------------------------------|
| Was ist XSS?      | Schadcode wird durch Nutzer in Webseiten eingeschleust  |
| Arten             | Stored, Reflected, DOM-based                             |
| Schutz            | Escaping, CSP, sicheres DOM-Handling, Frameworks nutzen |
| Wichtig!          | **Jede Benutzereingabe ist potenziell gefährlich!**     |

---

## 🔗 Weitere Ressourcen

- [OWASP XSS Cheat Sheet](https://owasp.org/www-community/xss)
- [MDN – Cross-site scripting](https://developer.mozilla.org/en-US/docs/Glossary/Cross-site_scripting)

> 🧠 Tipp: XSS ist die häufigste Schwachstelle im Web – **nimm sie ernst!**