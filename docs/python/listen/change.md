# 🔧 Listen verändern (Change / Modify)

Listen in Python sind **veränderbare (mutable)** Datenstrukturen.  
Du kannst Elemente **ändern, einfügen, anhängen oder löschen** – direkt und flexibel.

---

## ✍️ 1. Einzelne Werte ändern

Du kannst den Wert eines bestimmten Elements **per Index überschreiben**:

```python
farben = ["rot", "grün", "blau"]
farben[1] = "gelb"
print(farben)  # ['rot', 'gelb', 'blau']
```

---

## 🔁 2. Mehrere Werte mit Slicing ändern

```python
zahlen = [1, 2, 3, 4, 5]
zahlen[1:4] = [20, 30, 40]
print(zahlen)  # [1, 20, 30, 40, 5]
```

> Du kannst auch die Anzahl der Elemente ändern – z. B. mehr oder weniger einsetzen als zuvor.

---

## ➕ 3. Elemente hinzufügen

| Methode        | Beschreibung                         |
|----------------|--------------------------------------|
| `append(x)`    | Fügt `x` **hinten** an                |
| `insert(i, x)` | Fügt `x` an Position `i` ein         |
| `extend([...])`| Fügt mehrere Elemente hinzu          |

### Beispiele:

```python
farben.append("orange")
farben.insert(1, "violett")
farben.extend(["weiß", "schwarz"])
```

➡️ Ergebnis: `['rot', 'violett', 'gelb', 'blau', 'orange', 'weiß', 'schwarz']`

---

## ❌ 4. Elemente löschen

| Methode       | Beschreibung                          |
|---------------|---------------------------------------|
| `remove(x)`   | Entfernt **erstes** Vorkommen von `x` |
| `pop(i)`      | Entfernt Element bei Index `i`        |
| `del liste[i]`| Entfernt mit `del`                    |
| `clear()`     | Leert die ganze Liste                 |

### Beispiele:

```python
farben.remove("gelb")
farben.pop(0)         # entfernt erstes Element
del farben[-1]        # entfernt letztes
farben.clear()        # löscht alles
```

---

## ♻️ 5. Elemente tauschen

```python
farben = ["blau", "rot"]
farben[0], farben[1] = farben[1], farben[0]
print(farben)  # ['rot', 'blau']
```

---

## 🔁 6. Reihenfolge ändern

```python
farben = ["gelb", "grün", "rot"]
farben.reverse()     # ['rot', 'grün', 'gelb']
farben.sort()        # ['gelb', 'grün', 'rot']
farben.sort(reverse=True)  # ['rot', 'grün', 'gelb']
```

---

## 🧪 7. Inhalte ersetzen mit Schleifen

```python
zahlen = [1, 2, 3, 4, 5]

for i in range(len(zahlen)):
    zahlen[i] = zahlen[i] * 10

print(zahlen)  # [10, 20, 30, 40, 50]
```

---

## ✅ Zusammenfassung

| Aktion              | Methode/Beispiel                |
|---------------------|---------------------------------|
| Wert ändern         | `liste[1] = "neu"`              |
| Bereich ändern      | `liste[1:3] = [x, y]`           |
| Hinten anhängen     | `append(x)`                     |
| Einfügen an Stelle  | `insert(i, x)`                  |
| Mehrere hinzufügen  | `extend([...])`                 |
| Löschen nach Wert   | `remove(x)`                     |
| Löschen nach Index  | `pop(i)`, `del liste[i]`        |
| Leeren              | `clear()`                       |
| Tauschen            | `liste[a], liste[b] = liste[b], liste[a]` |
| Umkehren            | `reverse()`                     |
| Sortieren           | `sort()` / `sort(reverse=True)` |

---

> 🧠 Tipp: Listen sind dynamisch – du kannst jederzeit **größer, kleiner oder komplett anders** machen.