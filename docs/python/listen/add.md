# ➕ Listen erweitern (Add / Append / Insert)

Python-Listen sind **dynamisch**: Du kannst jederzeit **einzelne oder mehrere Elemente hinzufügen** – vorn, hinten oder dazwischen.

---

## 🔹 1. `append()` – Ein einzelnes Element **anhängen**

Fügt **ein Element am Ende** der Liste hinzu.

```python
tiere = ["Hund", "Katze"]
tiere.append("Maus")
print(tiere)  # ['Hund', 'Katze', 'Maus']
```

- Nur **ein Element pro Aufruf**
- Auch komplexe Elemente wie Listen, Dictionaries, etc.

```python
tiere.append(["Frosch", "Bär"])
print(tiere)  # ['Hund', 'Katze', 'Maus', ['Frosch', 'Bär']]
```

> ⛔ Achtung: Es wird **eine Liste als ein Element** angehängt!

---

## 🔹 2. `extend()` – **Mehrere Elemente** anhängen

Fügt **alle Elemente einer Liste einzeln** hinzu.

```python
zahlen = [1, 2, 3]
zahlen.extend([4, 5, 6])
print(zahlen)  # [1, 2, 3, 4, 5, 6]
```

> ✅ Ideal, um zwei Listen zu verbinden!

---

## 🔹 3. `insert(index, element)` – **Einfügen an beliebiger Stelle**

Setzt ein Element **vor** dem angegebenen Index.

```python
farben = ["rot", "blau"]
farben.insert(1, "grün")
print(farben)  # ['rot', 'grün', 'blau']
```

> 🧠 Der Index bestimmt die **Position vor dem neuen Element**.

---

## 🔹 4. `+=` Operator – Kurzform von `extend()`

```python
zahlen = [1, 2]
zahlen += [3, 4]
print(zahlen)  # [1, 2, 3, 4]
```

---

## 🔸 Unterschied `append()` vs. `extend()`

```python
liste = [1, 2]

liste.append([3, 4])
# → [1, 2, [3, 4]]  → Liste in Liste!

liste = [1, 2]
liste.extend([3, 4])
# → [1, 2, 3, 4]    → Flach eingefügt
```

| Methode    | Ergebnis                                 |
|------------|------------------------------------------|
| `append()` | Fügt **1 Element** (beliebigen Typs) an  |
| `extend()` | Fügt **mehrere Werte** (aus Liste) an    |

---

## 🧠 Tipps

- Du kannst `.append()` auch in Schleifen nutzen:
  
```python
ergebnis = []
for i in range(5):
    ergebnis.append(i * 10)

print(ergebnis)  # [0, 10, 20, 30, 40]
```

- `.insert()` ist nützlich für Sortier- oder Positionierungslogik

---

## ✅ Zusammenfassung

| Methode       | Zweck                                   | Beispiel                           |
|---------------|------------------------------------------|------------------------------------|
| `append(x)`   | Hängt `x` als Element hinten an          | `liste.append(7)`                  |
| `extend([...])`| Fügt alle Werte einer Liste hinzu       | `liste.extend([8, 9])`             |
| `insert(i, x)`| Fügt `x` an Position `i` ein             | `liste.insert(1, "grün")`          |
| `+=`          | Kurzform von `extend()`                  | `liste += [10, 11]`                |

---

> 🧩 Alle Methoden verändern die Liste **direkt** (in-place) und geben **kein Ergebnis zurück**.