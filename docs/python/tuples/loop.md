# 🔁 Loop über Tuples

Auch wenn Tuples **unveränderlich (immutable)** sind, kannst du sie **problemlos durchlaufen**, z. B. mit einer `for`-Schleife. So kannst du auf jedes Element zugreifen – genau wie bei Listen.

---

## 🧩 Einfaches Durchlaufen mit `for`

```python
farben = ("rot", "grün", "blau")

for farbe in farben:
    print(farbe)
```

➡️ Ausgabe:

```
rot  
grün  
blau
```

---

## 🔢 Mit Index (`range` + `len()`)

Wenn du **Index und Wert** brauchst:

```python
farben = ("rot", "grün", "blau")

for i in range(len(farben)):
    print(f"Index {i}: {farben[i]}")
```

➡️ Ausgabe:

```
Index 0: rot  
Index 1: grün  
Index 2: blau
```

---

## 🧠 `enumerate()` – Index und Wert gleichzeitig

```python
farben = ("rot", "grün", "blau")

for index, farbe in enumerate(farben):
    print(f"{index}: {farbe}")
```

➡️ Ausgabe:

```
0: rot  
1: grün  
2: blau
```

---

## 🔄 Tuple von Tuples durchlaufen

```python
personen = (("Anna", 30), ("Ben", 25), ("Clara", 28))

for name, alter in personen:
    print(f"{name} ist {alter} Jahre alt")
```

➡️ Ausgabe:

```
Anna ist 30 Jahre alt  
Ben ist 25 Jahre alt  
Clara ist 28 Jahre alt
```

---

## 🔀 Auch mit `while`-Schleife

```python
farben = ("rot", "grün", "blau")
i = 0

while i < len(farben):
    print(farben[i])
    i += 1
```

---

## 📌 Typische Anwendungsfälle

| Anwendung               | Technik                         |
|--------------------------|---------------------------------|
| Alle Werte ausgeben      | `for x in tuple:`              |
| Index und Wert           | `enumerate()` verwenden        |
| Zugriff per Index        | `range(len(tuple))`            |
| Entpackung in Schleife   | `for a, b in tuple_of_tuples:` |

---

## 🚫 Achtung: Tuple ist **nicht veränderbar**

Obwohl du die Werte lesen kannst, darfst du sie **nicht ändern**:

```python
farben[0] = "gelb"  # ❌ TypeError!
```

---

## ✅ Zusammenfassung

| Schleife       | Zweck                              |
|----------------|-------------------------------------|
| `for x in t`   | Alle Werte nacheinander lesen      |
| `for i in range()` | Indexbasiertes Durchlaufen     |
| `enumerate()`  | Index & Wert kombiniert            |
| `while`        | Falls komplexere Bedingungen nötig |

---

> 💡 Tuples sind perfekt für **fixe Datensätze**, die du **durchlaufen aber nicht ändern** willst.