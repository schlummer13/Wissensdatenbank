# 🧰 Set-Methoden (Methodenübersicht)

Sets (`set`) sind **ungeordnete Sammlungen eindeutiger Elemente**. Python stellt viele Methoden bereit, um Sets zu verändern, zu kombinieren oder zu vergleichen.

---

## 📦 Grundlegende Methoden

### 🔹 `add()` – Element hinzufügen

```python
farben = {"rot", "blau"}
farben.add("grün")
print(farben)  # {"rot", "blau", "grün"}
```

- Fügt **ein einzelnes Element** hinzu
- Duplikate werden ignoriert

---

### 🔹 `update()` – mehrere Elemente hinzufügen

```python
zahlen = {1, 2}
zahlen.update([2, 3, 4])
print(zahlen)  # {1, 2, 3, 4}
```

- Fügt **mehrere Elemente** hinzu
- Auch `list`, `tuple`, `set`, `dict` verwendbar

---

## 🗑️ Entfernen von Elementen

### 🔸 `remove()` – Element löschen

```python
farben = {"rot", "blau"}
farben.remove("blau")
```

- ❗ Fehler, wenn das Element nicht existiert (`KeyError`)

---

### 🔸 `discard()` – sicher löschen

```python
farben = {"rot", "blau"}
farben.discard("grün")  # kein Fehler!
```

- Kein Fehler, wenn Element nicht existiert

---

### 🔸 `pop()` – zufälliges Element entfernen

```python
zahlen = {1, 2, 3}
entfernt = zahlen.pop()
print(entfernt)  # z. B. 2
```

- Entfernt **irgendein** Element (weil Sets ungeordnet sind)

---

### 🔸 `clear()` – alles löschen

```python
zahlen = {1, 2, 3}
zahlen.clear()
print(zahlen)  # set()
```

---

## 🔍 Set-Vergleiche & Operationen

### `union()` / `|` – Vereinigung

```python
a = {1, 2}
b = {2, 3}
print(a.union(b))  # {1, 2, 3}
```

---

### `intersection()` / `&` – Schnittmenge

```python
a = {1, 2}
b = {2, 3}
print(a.intersection(b))  # {2}
```

---

### `difference()` / `-` – Differenz

```python
a = {1, 2, 3}
b = {2, 3}
print(a.difference(b))  # {1}
```

---

### `symmetric_difference()` / `^` – Symmetrische Differenz

```python
a = {1, 2}
b = {2, 3}
print(a.symmetric_difference(b))  # {1, 3}
```

---

## ✅ Vergleichsmethoden

| Methode                      | Bedeutung                                        |
|------------------------------|--------------------------------------------------|
| `issubset(other)`            | Ist dieses Set vollständig in `other` enthalten? |
| `issuperset(other)`          | Enthält dieses Set alle von `other`?             |
| `isdisjoint(other)`          | Haben beide **keine** gemeinsamen Elemente?      |

**Beispiel:**

```python
a = {1, 2}
b = {1, 2, 3}
print(a.issubset(b))     # True
print(b.issuperset(a))   # True
print(a.isdisjoint({4})) # True
```

---

## 🧠 Zusammenfassung

| Kategorie       | Methoden                                   |
|------------------|--------------------------------------------|
| Hinzufügen       | `add()`, `update()`                       |
| Entfernen        | `remove()`, `discard()`, `pop()`, `clear()` |
| Operationen      | `union()`, `intersection()`, `difference()`, `symmetric_difference()` |
| Vergleiche       | `issubset()`, `issuperset()`, `isdisjoint()` |

---

> 💡 Set-Methoden sind ideal für **Mengenlogik, Datenfilterung, Duplikat-Entfernung und mathematische Vergleiche**.