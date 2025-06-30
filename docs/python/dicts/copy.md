# 📝 Dictionaries kopieren (`dict copy`)

Ein Dictionary (`dict`) zu kopieren ist wichtig, wenn du das Original **nicht verändern willst**, aber mit denselben Daten arbeiten möchtest.

---

## 📋 1. Kopieren mit `.copy()`

```python
original = {"name": "Anna", "alter": 28}
kopie = original.copy()

kopie["alter"] = 30

print(original)  # {'name': 'Anna', 'alter': 28}
print(kopie)     # {'name': 'Anna', 'alter': 30}
```

✅ Erstellt eine **flache Kopie**
✅ Änderungen an der Kopie beeinflussen das Original **nicht**

---

## 🟡 Vorsicht bei verschachtelten Dictionaries

```python
daten = {
  "name": "Max",
  "adresse": {"stadt": "Berlin", "plz": "10115"}
}

flach = daten.copy()
flach["adresse"]["stadt"] = "Hamburg"

print(daten["adresse"]["stadt"])  # Hamburg 😱
```

🔸 Warum? → `.copy()` kopiert **nur die oberste Ebene** – die inneren Objekte sind **referenziert** (nicht dupliziert)

---

## 📦 2. Tiefe Kopie mit `copy.deepcopy()`

```python
import copy

daten = {
  "name": "Max",
  "adresse": {"stadt": "Berlin", "plz": "10115"}
}

tief = copy.deepcopy(daten)
tief["adresse"]["stadt"] = "Hamburg"

print(daten["adresse"]["stadt"])  # Berlin 👍
```

✅ **Echte Kopie aller Ebenen**
✅ Keine gemeinsamen Referenzen mehr

---

## ✂️ 3. Manuell duplizieren (nicht empfohlen)

```python
original = {"a": 1, "b": 2}
kopie = dict(original)  # auch flache Kopie
```

➡️ Funktioniert, aber `.copy()` ist lesbarer & gängiger

---

## 🔍 `=` ist keine Kopie!

```python
a = {"x": 1}
b = a
b["x"] = 2

print(a)  # {'x': 2} 😱
```

➡️ Beide zeigen auf dasselbe Objekt im Speicher – Änderungen wirken **beidseitig**

---

## ✅ Zusammenfassung

| Methode                | Typ               | Ebenen | Empfohlen |
|------------------------|-------------------|--------|-----------|
| `dict.copy()`          | Flach             | 1      | ✅ Ja     |
| `copy.deepcopy(dict)`  | Tief (rekursiv)   | ∞      | ✅ Ja     |
| `dict(a)`              | Flach             | 1      | ⚠️ ok     |
| `b = a`                | Referenz          | -      | ❌ Nein   |

---

> 🧠 Wenn du mit **mehrdimensionalen oder verschachtelten Daten** arbeitest, ist `deepcopy()` deine beste Wahl. Für einfache Kopien reicht `.copy()` aus.