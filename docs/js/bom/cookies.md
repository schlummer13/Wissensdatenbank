# 🍪 BOM – Cookies

## 🧩 Was sind Cookies?

**Cookies** sind kleine Textinformationen, die im Browser gespeichert werden, um Daten **zwischen Seitenaufrufen** zu behalten.  
Sie werden typischerweise verwendet für:

- Benutzer-Logins
- Session-IDs
- Spracheinstellungen
- Tracking und Analytics

> Cookies bestehen aus Schlüssel-Wert-Paaren und werden automatisch mit jeder HTTP-Anfrage an den Server gesendet (außer `HttpOnly`).

---

## ✅ Einfache Cookie-Erstellung

```js
document.cookie = "username=Florian";
```

📝 Diese Zeile speichert den Cookie `username=Florian` im Browser.

---

## 📅 Ablaufdatum setzen (expires)

```js
document.cookie = "user=Anna; expires=Fri, 31 Dec 2025 23:59:59 GMT";
```

- Nach Ablauf wird der Cookie automatisch gelöscht.
- Ohne `expires` oder `max-age` → Session-Cookie (löscht sich beim Schließen des Browsers).

---

## 🕐 Alternativ: `max-age`

```js
document.cookie = "theme=dark; max-age=3600"; // 1 Stunde
```

---

## 🌐 Domain & Pfad

```js
document.cookie = "info=test; path=/; domain=example.com";
```

- `path=/admin` → Nur gültig auf bestimmten Pfaden
- `domain=example.com` → Auch für Subdomains

---

## 🔒 Sicherheit (optional)

| Attribut    | Beschreibung                                |
|-------------|---------------------------------------------|
| `secure`    | Nur über HTTPS senden                       |
| `SameSite`  | Cookie-Schutz bei Cross-Site Requests       |
| `HttpOnly`  | Nur über HTTP, nicht über JavaScript zugänglich |

---

## 🔎 Cookies lesen

```js
console.log(document.cookie);
// "username=Florian; theme=dark"
```

➡️ Du bekommst einen String mit **allen Cookies** der aktuellen Seite.

Um einzelne Werte zu extrahieren, musst du sie parsen:

```js
function getCookie(name) {
  const cookies = document.cookie.split("; ");
  for (let cookie of cookies) {
    const [key, value] = cookie.split("=");
    if (key === name) return value;
  }
  return null;
}

getCookie("username"); // z. B. "Florian"
```

---

## ❌ Cookie löschen

Ein Cookie löschen = mit gleichem Namen + `expires` in der Vergangenheit:

```js
document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 UTC;";
```

---

## 🧠 Tipps

- Cookies sind **maximal 4 KB groß**
- Nutze sie **nicht für sensible Daten** (z. B. Passwörter!)
- Bei neuen Cookies **immer `path` und `expires` mitdenken**
- Für komplexere Speicherung: lieber **`localStorage`** oder **`sessionStorage`** verwenden

---

## ✅ Zusammenfassung

| Aktion             | Beispielcode                                      |
|--------------------|---------------------------------------------------|
| Cookie setzen      | `document.cookie = "key=value"`                  |
| Ablaufdatum setzen | `; expires=...` oder `; max-age=...`             |
| Cookie lesen       | `document.cookie` oder eigene Funktion            |
| Cookie löschen     | `expires=Vergangenheit` setzen                    |
| Sicherheitsflags   | `; secure; HttpOnly; SameSite=Strict`            |

