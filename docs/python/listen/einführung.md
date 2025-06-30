# 📚 Einführung in Listen

Listen sind **eine der wichtigsten und meistgenutzten Datenstrukturen** in Python.  
Sie ermöglichen es dir, **mehrere Werte in einer geordneten Sequenz** zu speichern – egal ob Zahlen, Texte oder andere Objekte.

---

## 🧩 Was ist eine Liste?

Eine Liste ist eine **veränderbare Sammlung** von Werten (Elementen), die du in **eckige Klammern `[]`** schreibst.

```python
meine_liste = [1, 2, 3, 4, 5]
namen = ["Anna", "Ben", "Clara"]
gemischt = [42, "Text", True, 3.14]
```

- Reihenfolge bleibt **erhalten**
- Du kannst **beliebige Datentypen** mischen
- Du kannst **Einträge verändern, hinzufügen, löschen**

---

## 🔍 Auf einzelne Werte zugreifen

```python
zahlen = [10, 20, 30]

print(zahlen[0])  # → 10
print(zahlen[2])  # → 30
```

> Achtung: Der Index beginnt bei **0**

---

## 🔁 Durch Listen iterieren

```python
for name in ["Tom", "Lena", "Ali"]:
    print("Hallo", name)
```

---

## 🧱 Listen verschachteln (Nested Lists)

Listen können andere Listen enthalten:

```python
matrix = [[1, 2], [3, 4]]
print(matrix[1][0])  # → 3
```

---

## ➕ Neue Werte hinzufügen

| Methode           | Beschreibung                              |
|-------------------|-------------------------------------------|
| `append(x)`       | Hängt **ein** Element hinten an            |
| `insert(i, x)`    | Fügt an Position `i` ein                   |
| `extend([...])`   | Fügt mehrere Elemente an                   |

```python
liste = [1, 2]
liste.append(3)       # [1, 2, 3]
liste.insert(1, 9)    # [1, 9, 2, 3]
liste.extend([4, 5])  # [1, 9, 2, 3, 4, 5]
```

---

## ❌ Werte entfernen

| Methode         | Beschreibung                            |
|------------------|-----------------------------------------|
| `remove(x)`     | Entfernt den **ersten** Treffer von `x` |
| `pop(i)`        | Entfernt und gibt Wert bei Index `i` zurück |
| `clear()`       | Leert die Liste komplett                |

```python
liste = [1, 2, 3, 2]
liste.remove(2)  # → entfernt das erste `2`
liste.pop()      # → entfernt das letzte Element
liste.clear()    # → []
```

---

## 🔄 Werte ändern

```python
farben = ["rot", "grün", "blau"]
farben[1] = "gelb"  # ["rot", "gelb", "blau"]
```

---

## 🔍 Prüfen, ob etwas enthalten ist

```python
if "blau" in farben:
    print("Blau ist vorhanden!")
```

---

## 🧪 Länge & Zählen

```python
len(farben)           # Anzahl der Elemente
farben.count("rot")   # Wie oft kommt "rot" vor?
```

---

## 📦 Listen kopieren

```python
kopie = farben.copy()
```

> Kein Alias, sondern echte Kopie!

---

## 🔀 Sortieren & Umkehren

```python
zahlen = [3, 1, 4]
zahlen.sort()      # [1, 3, 4]
zahlen.reverse()   # [4, 3, 1]
```

> Achtung: `.sort()` verändert die Liste!

---

## ✅ Zusammenfassung

| Aktion            | Methode/Beispiel                    |
|-------------------|-------------------------------------|
| Erstellen         | `[]`, `list()`                      |
| Zugriff           | `liste[0]`, Schleife                |
| Hinzufügen        | `append()`, `insert()`, `extend()`  |
| Entfernen         | `remove()`, `pop()`, `clear()`      |
| Prüfen            | `"x" in liste`                      |
| Länge             | `len(liste)`                        |
| Sortieren         | `sort()`, `reverse()`               |
| Kopieren          | `copy()`                            |

---

> 🧠 Tipp: Listen sind **veränderbar** (mutable) – das unterscheidet sie z. B. von **Tuples**.