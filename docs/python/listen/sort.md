# 🔢 Listen sortieren (`sort()` & `sorted()`)

Python bietet **zwei Hauptmethoden**, um Listen zu sortieren:  
🔹 **`list.sort()`** – verändert die Liste direkt  
🔹 **`sorted()`** – erstellt eine neue, sortierte Liste

---

## 🧩 Beispiel: Einfache Sortierung

```python
zahlen = [5, 2, 9, 1]
zahlen.sort()
print(zahlen)  # [1, 2, 5, 9]
```

- **Sortiert dauerhaft** (in-place)
- Verändert die ursprüngliche Liste

---

## 🔁 `sorted()` – Rückgabe einer neuen Liste

```python
zahlen = [3, 1, 4]
neu = sorted(zahlen)
print(neu)       # [1, 3, 4]
print(zahlen)    # [3, 1, 4] bleibt unverändert
```

➡️ Nützlich, wenn du das Original behalten möchtest

---

## 🔽 Absteigend sortieren

```python
zahlen = [4, 2, 8]
zahlen.sort(reverse=True)
print(zahlen)  # [8, 4, 2]
```

Oder mit `sorted()`:

```python
sorted(zahlen, reverse=True)
```

---

## 🔤 Strings alphabetisch sortieren

```python
woerter = ["Banane", "Apfel", "Zitrone"]
woerter.sort()
print(woerter)  # ['Apfel', 'Banane', 'Zitrone']
```

### Case-sensitive?

```python
["z", "a", "A"].sort()
# Ergebnis: ['A', 'a', 'z']  → Groß vor klein
```

---

## 🧠 Mit Schlüssel (Key-Funktion) sortieren

### Beispiel: Nach Länge sortieren

```python
woerter = ["Haus", "Schnecke", "Ei"]
woerter.sort(key=len)
print(woerter)  # ['Ei', 'Haus', 'Schnecke']
```

---

### Beispiel: Nach letzter Ziffer

```python
zahlen = [23, 45, 12, 38]
zahlen.sort(key=lambda x: x % 10)
print(zahlen)  # [12, 23, 45, 38]
```

---

### Wörter unabhängig von Groß-/Kleinschreibung

```python
woerter = ["Zebra", "apfel", "Banane"]
woerter.sort(key=str.lower)
print(woerter)  # ['apfel', 'Banane', 'Zebra']
```

---

## 🔄 Objekte / Dictionaries sortieren

### Liste von Dictionaries

```python
personen = [
    {"name": "Max", "alter": 30},
    {"name": "Anna", "alter": 25},
]

personen.sort(key=lambda x: x["alter"])
```

➡️ Sortiert nach Alter aufsteigend

---

## 📌 Unterschiede: `sort()` vs `sorted()`

| Merkmal        | `list.sort()`         | `sorted()`              |
|----------------|------------------------|--------------------------|
| Typ            | **Methode** der Liste | **Funktion**             |
| Wirkung        | Ändert Original        | Gibt neue Liste zurück   |
| Rückgabewert   | `None`                 | Neue sortierte Liste     |
| Auf alle Typen | ❌ nur Listen          | ✅ für jedes Iterierbare |

---

## ✅ Zusammenfassung

| Aufgabe                  | Methode                            |
|--------------------------|-------------------------------------|
| Liste dauerhaft sortieren | `list.sort()`                      |
| Neue sortierte Liste      | `sorted(iterable)`                 |
| Absteigend sortieren      | `sort(reverse=True)`               |
| Nach Eigenschaft sortieren| `sort(key=...)`                    |
| Case-insensitiv           | `key=str.lower`                    |

---

> 💡 `sorted()` ist ideal für einmalige Sortierung – `sort()` spart Speicher & ist schneller.