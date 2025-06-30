# 🔁 Dictionaries durchlaufen (`dict loop`)

Dictionaries (`dict`) können **Schlüssel**, **Werte** oder **beides gleichzeitig** iterieren. Ideal, um Daten auszulesen, zu verarbeiten oder anzuzeigen.

---

## 🔑 Nur Schlüssel (`for key in dict`)

```python
person = {"name": "Anna", "alter": 28}

for key in person:
    print(key)
```

➡️ Gibt aus:

```
name
alter
```

💡 Entspricht `for key in person.keys()`

---

## 🔢 Nur Werte (`for value in dict.values()`)

```python
for value in person.values():
    print(value)
```

➡️ Gibt aus:

```
Anna
28
```

---

## 🔐 Schlüssel & Werte (`for key, value in dict.items()`)

```python
for key, value in person.items():
    print(f"{key}: {value}")
```

➡️ Gibt aus:

```
name: Anna
alter: 28
```

---

## 🧠 Typische Anwendungen

### 🔍 Bestimmte Werte überprüfen

```python
for value in person.values():
    if value == "Anna":
        print("Name gefunden!")
```

---

### 🧮 Einträge zählen

```python
count = 0
for _ in person:
    count += 1
print("Anzahl Einträge:", count)
```

---

## 📚 Mit Bedingungen kombinieren

```python
for key in person:
    if key.startswith("a"):
        print(f"{key}: {person[key]}")
```

➡️ Gibt nur Einträge aus, deren Schlüssel mit "a" beginnen

---

## 📦 Geschachtelte Dictionaries durchlaufen

```python
personen = {
    "max": {"alter": 25, "stadt": "Berlin"},
    "lisa": {"alter": 30, "stadt": "Hamburg"}
}

for name, daten in personen.items():
    print(f"{name} lebt in {daten['stadt']} und ist {daten['alter']} Jahre alt.")
```

---

## ✅ Zusammenfassung

| Ziel                   | Syntax                                |
|------------------------|----------------------------------------|
| Nur Schlüssel          | `for key in dict:`                    |
| Nur Werte              | `for value in dict.values():`         |
| Schlüssel & Wert       | `for key, value in dict.items():`     |
| Geschachtelte Dicts    | Mit verschachtelten Loops oder Zugriffen |
| Bedingte Filterung     | Mit `if` im Loop kombinieren          |

---

> 🔁 Mit `items()` wird das Dictionary am flexibelsten durchlaufen – besonders bei Datenanalyse, Transformation oder dynamischem Zugriff.