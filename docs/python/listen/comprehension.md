# 🧠 List Comprehension

**List Comprehension** ist eine kompakte und elegante Möglichkeit, **Listen zu erstellen** oder **umzuwandeln**, ohne eine klassische Schleife zu verwenden.

> 🔥 Schnell, lesbar und sehr mächtig – ideal für viele typische Aufgaben mit Listen!

---

## 🧩 Grundstruktur

```python
[ausdruck for element in iterable]
```

### Beispiel:

```python
zahlen = [1, 2, 3, 4]
quadrate = [x * x for x in zahlen]
print(quadrate)  # [1, 4, 9, 16]
```

---

## ✅ Vorteile

- **Weniger Code**
- **Lesbarer** als klassische Schleifen
- **Schneller** in der Ausführung
- Einfach mit **Bedingungen** kombinierbar

---

## 🔹 Mit Bedingung (`if`)

```python
gerade = [x for x in range(10) if x % 2 == 0]
print(gerade)  # [0, 2, 4, 6, 8]
```

➡️ Nur gerade Zahlen aufnehmen

---

## 🔹 Mit `if`–`else` (ternärer Ausdruck)

```python
werte = [x if x % 2 == 0 else -x for x in range(5)]
print(werte)  # [0, -1, 2, -3, 4]
```

➡️ Bedingte Verarbeitung für jedes Element

---

## 🔹 Strings verarbeiten

```python
text = "Python"
buchstaben = [buchstabe.upper() for buchstabe in text]
print(buchstaben)  # ['P', 'Y', 'T', 'H', 'O', 'N']
```

---

## 🔹 Verschachtelte Schleifen

```python
kombis = [(x, y) for x in [1, 2] for y in [3, 4]]
print(kombis)  # [(1, 3), (1, 4), (2, 3), (2, 4)]
```

➡️ Alle Kombinationen erzeugen

---

## 🔹 Mit Funktionen kombinieren

```python
def quadrat(x):
    return x * x

liste = [quadrat(n) for n in range(5)]
print(liste)  # [0, 1, 4, 9, 16]
```

---

## 🔹 Mit Dictionary & Set Comprehension

| Typ             | Beispiel                                  |
|------------------|--------------------------------------------|
| **List**         | `[x*2 for x in liste]`                     |
| **Set**          | `{x*2 for x in liste}`                     |
| **Dictionary**   | `{x: x**2 for x in range(5)}`              |

---

## 🔹 Mit Enumerate & Bedingungen

```python
daten = ["", "Text", "", "Wert"]
nicht_leer = [x for i, x in enumerate(daten) if x]
print(nicht_leer)  # ['Text', 'Wert']
```

---

## ⚠️ Vorsicht bei komplexen Ausdrücken

List Comprehension sollte **lesbar** bleiben!

```python
# Zu kompliziert → besser normale Schleife!
```

---

## 🧠 Zusammenfassung

| Möglichkeit                     | Beispiel                              |
|----------------------------------|----------------------------------------|
| Basis                           | `[x for x in range(10)]`              |
| Mit Bedingung                   | `[x for x in liste if x > 0]`         |
| Mit if–else                     | `[x if x > 0 else 0 for x in liste]`  |
| Mit verschachtelter Schleife    | `[(x, y) for x in a for y in b]`      |
| Set / Dict                      | `{x for x in liste}`, `{k: v for ...}`|

---

> 💡 List Comprehensions sind **perfekt für einfache Umwandlungen** – spare dir unnötige Schleifen!