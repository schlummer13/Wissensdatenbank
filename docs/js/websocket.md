# 🌐 WebSockets

WebSockets ermöglichen eine **dauerhafte, bidirektionale Verbindung** zwischen Client (Browser) und Server. Ideal für **Live-Daten**, wie Chats, Echtzeit-Updates, Spiele, Börsenkurse oder IoT.

> Anders als `fetch` oder `AJAX` basiert WebSocket **nicht auf einzelnen HTTP-Anfragen**, sondern auf einem **offenen Kanal**, der Daten jederzeit senden und empfangen kann.

---

## 🧩 Was ist ein WebSocket?

Ein **Protokoll** (`ws://` oder `wss://`), das den ständigen Austausch zwischen Client und Server ermöglicht:

- Schnell
- Geringe Latenz
- Beidseitig (Client ↔ Server)
- Ideal für Realtime-Kommunikation

---

## 🔌 Verbindung aufbauen

```js
const socket = new WebSocket("wss://echo.websocket.org");

socket.onopen = () => {
  console.log("✅ Verbindung geöffnet");
  socket.send("Hallo Server!");
};

socket.onmessage = (event) => {
  console.log("📩 Nachricht erhalten:", event.data);
};

socket.onerror = (error) => {
  console.error("❌ Fehler:", error);
};

socket.onclose = () => {
  console.log("🔌 Verbindung geschlossen");
};
```

> `wss://` ist verschlüsselt (wie HTTPS), `ws://` ist unverschlüsselt (wie HTTP)

---

## 📦 Daten senden

```js
socket.send("Hallo Welt");
```

- Du kannst einfache Strings oder mit `JSON.stringify()` auch Objekte senden.

```js
socket.send(JSON.stringify({ benutzer: "Max", nachricht: "Hi!" }));
```

---

## 📥 Daten empfangen

```js
socket.onmessage = function(event) {
  const daten = event.data;
  console.log("Server sagt:", daten);
};
```

---

## ❌ Verbindung schließen

```js
socket.close();
```

Optionale Parameter:

```js
socket.close(1000, "Normales Ende");
```

---

## 🧪 Beispiel: Echo-Dienst (nur zu Testzwecken)

```js
const socket = new WebSocket("wss://echo.websocket.org");

socket.onopen = () => {
  socket.send("Testnachricht");
};

socket.onmessage = (event) => {
  alert("Antwort vom Server: " + event.data);
};
```

---

## 📘 Statuswerte

```js
socket.readyState
```

| Wert | Bedeutung          |
|------|---------------------|
| 0    | `CONNECTING`        |
| 1    | `OPEN`              |
| 2    | `CLOSING`           |
| 3    | `CLOSED`            |

---

## 🧠 JSON-Handling (typisch)

```js
socket.onmessage = (event) => {
  const daten = JSON.parse(event.data);
  console.log(daten.typ, daten.nachricht);
};
```

---

## 🛠 Anwendungsszenarien

- ✅ Chats
- 📈 Börsenticker
- 🎮 Echtzeit-Spiele
- 🛎️ Notifications
- 📡 IoT / Gerätekommunikation

---

## 🚧 Sicherheit beachten!

- **Verwende `wss://`** (WebSocket Secure)
- Authentifiziere Benutzer, z. B. mit Tokens
- Verwalte Timeouts & fehlerhafte Verbindungen
- Nutze Fallbacks (Long Polling etc.)

---

## 🔁 Reconnect-Logik (Basisidee)

```js
let socket;

function verbinde() {
  socket = new WebSocket("wss://example.com");

  socket.onclose = () => {
    console.log("Verbindung verloren. Neuer Versuch in 5 Sek...");
    setTimeout(verbinde, 5000);
  };
}

verbinde();
```

---

## ✅ Zusammenfassung

| Methode / Event     | Bedeutung                          |
|---------------------|-------------------------------------|
| `new WebSocket(url)`| Verbindung aufbauen                |
| `socket.send()`     | Nachricht senden                   |
| `socket.onmessage`  | Nachricht empfangen                |
| `socket.close()`    | Verbindung beenden                 |
| `onopen` / `onclose`| Verbindungsstatus überwachen       |
| `onerror`           | Fehlerbehandlung                   |
