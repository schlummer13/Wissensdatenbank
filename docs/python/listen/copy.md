# 📋 Listen kopieren (`copy()` & Co.)

Beim Arbeiten mit Listen in Python ist es wichtig zu wissen:  
**Eine direkte Zuweisung kopiert NICHT die Liste, sondern nur die Referenz!**  
Änderungen wirken sich dann auf beide aus.

---

## 🚫 Falsche Kopie (Referenz)

```python
original = [1, 2, 3]
kopie = original

kopie[0] = 99
print(original)  # [99, 2, 3] ❗️
```

➡️ **`kopie` zeigt auf dieselbe Liste wie `original`**

---

## ✅ Echte Kopie einer Liste

### 🔹 1. `list.copy()` – Flache Kopie (ab Python 3.3)

```python
original = [1, 2, 3]
kopie = original.copy()

kopie[0] = 99
print(original)  # [1, 2, 3] ✅
```

---

### 🔹 2. Slicing `[:]`

```python
original = ["a", "b", "c"]
kopie = original[:]

kopie.append("d")
print(original)  # ['a', 'b', 'c']
print(kopie)     # ['a', 'b', 'c', 'd']
```

---

### 🔹 3. `list()` Konstruktor

```python
original = [10, 20]
kopie = list(original)
```

---

### 🔹 4. `copy.copy()` – Standardmodul

```python
import copy
kopie = copy.copy(original)
```

➡️ Auch flache Kopie – ähnlich wie `list.copy()`

---

## 🧠 Flache vs. Tiefe Kopie

### Flache Kopie:
Nur **äußere Liste wird kopiert** – verschachtelte Objekte (z. B. Listen in Listen) bleiben **verlinkt**:

```python
liste = [[1, 2], [3, 4]]
kopie = liste.copy()
kopie[0][0] = 99

print(liste)  # [[99, 2], [3, 4]] ❗
```

### Tiefe Kopie (deep copy):

```python
import copy
liste = [[1, 2], [3, 4]]
kopie = copy.deepcopy(liste)

kopie[0][0] = 99
print(liste)  # [[1, 2], [3, 4]] ✅
```

---

## 🧪 Wann welche Methode?

| Methode            | Art            | Besonderheiten                   |
|--------------------|----------------|----------------------------------|
| `list.copy()`      | Flach          | Einfach, schnell, ab Python 3.3 |
| `[:]`              | Flach          | Funktioniert immer               |
| `list()`           | Flach          | Flexibel bei iterierbaren Objekten |
| `copy.copy()`      | Flach          | Aus dem `copy`-Modul             |
| `copy.deepcopy()`  | **Tief**       | Kopiert auch verschachtelte Objekte |

---

## ✅ Best Practice

- **Einfache Listen:** `list.copy()` oder `[:]`
- **Verschachtelte Listen / Objekte:** `copy.deepcopy()`

---

## 🧠 Bonus: Unterschied zu `=`

```python
a = [1, 2]
b = a       # KEINE Kopie! Nur Alias
c = a[:]    # Echte flache Kopie
```

> **Merke:** Nur bei expliziter Kopie werden zwei unabhängige Listen erstellt!