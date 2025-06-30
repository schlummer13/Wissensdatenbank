# 🎯 Tuple Zugriff (Access)

Ein **Tuple** ist eine **geordnete Sammlung**. Das bedeutet, dass du – wie bei Listen – über **Indizes** (Positionen) auf einzelne Werte zugreifen kannst.  

Da Tuples **unveränderlich (immutable)** sind, kannst du Werte **lesen**, aber **nicht ändern**.

---

## 🧩 Zugriff über Index

```python
farben = ("rot", "grün", "blau")

print(farben[0])  # rot
print(farben[1])  # grün
print(farben[2])  # blau
```

> ✅ Der Index beginnt bei **0**, nicht bei 1!

---

## 🔁 Negativer Index (von hinten zählen)

```python
farben = ("rot", "grün", "blau")

print(farben[-1])  # blau
print(farben[-2])  # grün
```

> 🔁 `-1` ist das letzte Element, `-2` das vorletzte usw.

---

## 🧵 Tuple durchlaufen (Iteration)

```python
zahlen = (10, 20, 30)

for zahl in zahlen:
    print(zahl)
```

➡️ Ausgabe:

```
10  
20  
30
```

---

## 🔍 Länge ermitteln

```python
zahlen = (1, 2, 3, 4)
print(len(zahlen))  # 4
```

> `len()` zählt, wie viele Elemente im Tuple sind.

---

## 🔍 Element prüfen mit `in`

```python
tiere = ("Hund", "Katze", "Maus")

print("Katze" in tiere)   # True
print("Vogel" in tiere)   # False
```

---

## 🧠 Warum nur Zugriff, kein Ändern?

Tuples sind **unveränderlich** – das heißt, du kannst **keine neuen Werte einfügen, entfernen oder überschreiben**.

```python
farben = ("rot", "grün", "blau")
farben[0] = "gelb"  # ❌ TypeError!
```

---

## 🧪 Tuple "entpacken"

```python
person = ("Max", 25, "Berlin")

name, alter, stadt = person

print(name)   # Max
print(alter)  # 25
print(stadt)  # Berlin
```

> Du kannst mehrere Werte aus einem Tuple **direkt in einzelne Variablen aufteilen**.

---

## 🧮 Zugriff auf Teilbereiche (Slicing)

```python
zahlen = (0, 1, 2, 3, 4)

print(zahlen[1:4])    # (1, 2, 3)
print(zahlen[:3])     # (0, 1, 2)
print(zahlen[2:])     # (2, 3, 4)
```

---

## 🔄 In Schleifen mit Index: `enumerate()`

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

## ✅ Zusammenfassung

| Technik           | Beschreibung                          |
|-------------------|----------------------------------------|
| `tuple[i]`        | Zugriff per Index                     |
| `tuple[-1]`       | Zugriff von hinten                    |
| `len(tuple)`      | Länge ermitteln                       |
| `"x" in tuple`    | Prüfen, ob Element enthalten ist       |
| `for x in tuple`  | Iteration durch Inhalte               |
| `a, b = tuple`    | Tuple entpacken                       |
| `tuple[i:j]`      | Teilbereiche per Slice                |

---

> 📌 **Merksatz**: Tuples sind wie Listen – nur festgefroren 🧊. Zugriff ja, ändern nein.