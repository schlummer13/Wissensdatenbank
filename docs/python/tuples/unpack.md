# 📦 Tuple Unpacking (Entpacken von Tuples)

Mit **Tuple Unpacking** kannst du die **einzelnen Werte eines Tuples direkt in eigene Variablen** speichern. Das macht den Code sauber, lesbar und elegant.

---

## 🧩 Einfaches Unpacking

```python
person = ("Max", 30, "Berlin")

name, alter, stadt = person

print(name)   # Max
print(alter)  # 30
print(stadt)  # Berlin
```

> ✅ Die Anzahl der Variablen muss genau zur Anzahl der Tuple-Werte passen.

---

## ⚠️ Zu viele oder zu wenige Variablen

```python
daten = ("Anna", 25)

# ❌ Fehler – 3 Variablen, aber nur 2 Werte
# name, alter, stadt = daten
# → ValueError: not enough values to unpack

# ✅ Korrekt
name, alter = daten
```

---

## 🔄 Mit Schleifen

```python
personen = [
    ("Max", 30),
    ("Lisa", 28),
    ("Tom", 25)
]

for name, alter in personen:
    print(f"{name} ist {alter} Jahre alt")
```

➡️ Ausgabe:

```
Max ist 30 Jahre alt  
Lisa ist 28 Jahre alt  
Tom ist 25 Jahre alt
```

---

## 🌟 Unpacking mit `_` (Ignorieren von Werten)

```python
person = ("Laura", 32, "München")

name, _, stadt = person
print(name)   # Laura
print(stadt)  # München
```

> Das `_` ist eine Konvention für: „Wert wird nicht gebraucht“

---

## ✨ Erweiterte Variante: `*` für den Rest

```python
zahlen = (1, 2, 3, 4, 5)

a, b, *rest = zahlen
print(a)      # 1
print(b)      # 2
print(rest)   # [3, 4, 5]
```

```python
*anfang, ende = (10, 20, 30, 40)
print(anfang)  # [10, 20, 30]
print(ende)    # 40
```

> Das `*` erlaubt es, **mehrere Werte** als Liste zu sammeln.

---

## 🔀 Nested Tuples entpacken

```python
daten = ("Anna", (1990, "Berlin"))

name, (jahr, stadt) = daten

print(name)  # Anna
print(jahr)  # 1990
print(stadt) # Berlin
```

---

## ✅ Zusammenfassung

| Technik                   | Beschreibung                               |
|---------------------------|--------------------------------------------|
| `a, b = tuple`            | Einfaches Unpacking                        |
| `a, _, c = tuple`         | Mittlerer Wert ignorieren                  |
| `a, *b = tuple`           | Rest in Liste sammeln                      |
| `*a, b = tuple`           | Anfang als Liste, letzter separat          |
| Nested: `(a, (b, c)) = …` | Verschachtelte Tuples entpacken            |

---

## 📌 Merksatz

> Unpacking ist wie Geschenke auspacken 🎁 –  
> Du weißt genau, was drin ist und legst es sauber ab.