# 🔁 Listen mit Schleifen durchlaufen

Listen enthalten oft mehrere Elemente – z. B. Zahlen, Strings oder Objekte.  
Mit Schleifen kannst du **jedes Element einzeln verarbeiten**.

---

## 🔹 1. `for`-Schleife – der Standardweg

```python
namen = ["Anna", "Ben", "Clara"]

for name in namen:
    print("Hallo", name)
```

➡️ Gibt aus:

```
Hallo Anna
Hallo Ben
Hallo Clara
```

- **Einfachster und empfohlener Weg**
- Läuft **automatisch** durch alle Elemente

---

## 🔹 2. `for` mit `range(len(...))` – für Index-Zugriff

```python
farben = ["rot", "blau", "grün"]

for i in range(len(farben)):
    print(f"Farbe an Position {i}: {farben[i]}")
```

➡️ Nützlich, wenn du den **Index brauchst**.

---

## 🔹 3. `enumerate()` – Index + Wert gemeinsam

```python
zahlen = [100, 200, 300]

for index, wert in enumerate(zahlen):
    print(f"Index {index} → {wert}")
```

➡️ Sauberer als `range(len(...))`

---

## 🔹 4. `while`-Schleife

```python
tiere = ["Hund", "Katze", "Maus"]
i = 0

while i < len(tiere):
    print(tiere[i])
    i += 1
```

> Verwende `while` nur, wenn du **flexibler zählen** oder **vorzeitig abbrechen** willst.

---

## 🔹 5. `list comprehension` – elegant & kompakt

```python
zahlen = [1, 2, 3, 4]
quadrate = [x * x for x in zahlen]
print(quadrate)  # [1, 4, 9, 16]
```

> Ideal für einfache Operationen **mit Rückgabe**

---

## 🔹 6. Schleife mit Bedingung

```python
zahlen = [5, 10, 15, 20]

for z in zahlen:
    if z > 10:
        print("Größer als 10:", z)
```

➡️ Kombinierbar mit `if`, `continue`, `break` usw.

---

## 🔹 7. `break`, `continue` und `return`

### `break` – Schleife abbrechen

```python
for x in [1, 2, 3, 4]:
    if x == 3:
        break
    print(x)  # 1, 2
```

### `continue` – aktuellen Durchlauf überspringen

```python
for x in [1, 2, 3, 4]:
    if x == 2:
        continue
    print(x)  # 1, 3, 4
```

### `return` – Funktion verlassen (nur in Funktionen!)

```python
def finde_zahl(liste):
    for x in liste:
        if x == 7:
            return True
    return False
```

---

## 🔹 Was kann man loopen?

| Typ        | Funktioniert mit `for`? |
|------------|--------------------------|
| Liste      | ✅                        |
| String     | ✅                        |
| Tuple      | ✅                        |
| Set        | ✅ (reihenfolgefrei)      |
| Dictionary | ✅ (Schlüssel werden gelistet) |

```python
# Dictionary
daten = {"name": "Max", "alter": 30}

for key in daten:
    print(key, "→", daten[key])
```

---

## ✅ Zusammenfassung

| Technik                 | Vorteil                                |
|-------------------------|----------------------------------------|
| `for element in liste`  | Einfachster Weg                        |
| `for i in range(len())`| Index-Zugriff                          |
| `enumerate()`           | Index + Wert in einem Schritt          |
| `while`                 | Flexible Bedingungen                   |
| List Comprehension      | Kompakt + schnell                      |
| `break`, `continue`     | Kontrolle über Schleifenfluss          |

---

> 💡 Für 95 % der Fälle ist `for element in liste:` der **beste und einfachste Weg**!