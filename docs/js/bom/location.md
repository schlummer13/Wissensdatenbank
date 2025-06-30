# 🌍 BOM – `location`

## 🧩 Was ist `location`?

Das `location`-Objekt gehört zum `window` und enthält **alle Informationen über die aktuelle URL**.  
Es erlaubt dir, die Seite **neu zu laden**, **weiterzuleiten** oder bestimmte **Teile der Adresse auszulesen oder zu ändern**.

👉 Du kannst damit z. B. prüfen, auf welcher Seite du bist – oder auf eine andere Seite umleiten.

---

## ✅ Zugriff

```js
console.log(window.location);
```

oder kürzer:

```js
console.log(location);
```

---

## 📚 Eigenschaften von `location`

| Eigenschaft     | Beschreibung                                    | Beispiel                                  |
|------------------|-------------------------------------------------|--------------------------------------------|
| `href`          | Gesamte URL                                     | `https://example.com/page?x=1#anker`       |
| `protocol`      | Protokoll (`http:`, `https:`)                   | `https:`                                   |
| `host`          | Domain + Port                                   | `example.com:443`                          |
| `hostname`      | Nur Domain                                      | `example.com`                              |
| `port`          | Port (optional)                                 | `443`                                      |
| `pathname`      | Pfad zur Seite                                  | `/page`                                    |
| `search`        | Query-Parameter                                 | `?x=1`                                     |
| `hash`          | Anker am Ende der URL                           | `#anker`                                   |
| `origin`        | Nur Basis (Protokoll + Host)                    | `https://example.com`                      |

---

## 🔄 Seite neu laden

```js
location.reload();      // Seite neu laden (aus Cache)
location.reload(true);  // Seite komplett neu laden (veraltet)
```

---

## 🔁 Weiterleitung zu anderer Seite

```js
location.href = "https://example.com";
```

⏱ Die Seite wird **sofort** weitergeleitet.

---

## 🔀 Navigation ohne Verlaufseintrag

```js
location.replace("https://example.com");
```

⏮ Kein "Zurück" im Verlauf möglich (ersetzt den aktuellen Eintrag).

---

## 🔍 Beispiel: Query-Parameter analysieren

```js
console.log(location.search); // ?name=florian&alter=32
```

➡ Du kannst mit `URLSearchParams` auswerten:

```js
const params = new URLSearchParams(location.search);
console.log(params.get("name")); // florian
```

---

## 🧠 Warum ist `location` wichtig?

- Für **dynamische Weiterleitungen**
- Um Inhalte anhand der **aktuellen Adresse** zu steuern
- Für **Routing in Single Page Apps (SPAs)**
- Um **Anker** (`#id`) zu verwenden

---

## ✅ Zusammenfassung

| Anwendungsfall         | Methode                                  |
|------------------------|-------------------------------------------|
| Aktuelle URL lesen     | `location.href`                           |
| Neue Seite laden       | `location.href = "..."`                   |
| Vollständige URL zerlegen | `protocol`, `host`, `pathname`, ...     |
| Seite neuladen         | `location.reload()`                       |
| Navigation ohne Verlauf | `location.replace("...")`                |

