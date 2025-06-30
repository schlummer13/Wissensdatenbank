# ❌ Elemente aus Listen entfernen

Listen sind **veränderbar** (mutable) – du kannst gezielt **einzelne oder mehrere Elemente löschen**.  
Python bietet verschiedene Methoden zum **Entfernen von Werten, Indexpositionen oder ganzen Listen**.

---

## 🔹 1. `remove()` – **Erstes Vorkommen** eines Wertes löschen

```python
farben = ["rot", "blau", "grün", "blau"]
farben.remove("blau")
print(farben)  # ['rot', 'grün', 'blau']
```

- Entfernt **nur das erste Vorkommen**
- Gibt **Fehler** bei nicht vorhandenem Wert:

```python
farben.remove("gelb")  # ❌ ValueError
```

---

## 🔹 2. `pop(index)` – Element **nach Index** entfernen

```python
zahlen = [10, 20, 30]
zahlen.pop(1)   # entfernt 20
print(zahlen)   # [10, 30]
```

- Gibt das **gelöschte Element zurück**
- Ohne Argument → entfernt **letztes** Element:

```python
zahlen.pop()  # entfernt 30
```

---

## 🔹 3. `del` – **Beliebige Stelle oder ganz löschen**

### Ein Element löschen:

```python
tiere = ["Hund", "Katze", "Maus"]
del tiere[1]
print(tiere)  # ['Hund', 'Maus']
```

### Bereich löschen (Slicing):

```python
zahlen = [1, 2, 3, 4, 5]
del zahlen[1:4]
print(zahlen)  # [1, 5]
```

### Ganze Liste löschen:

```python
del zahlen
```

> Danach ist `zahlen` **nicht mehr definiert**.

---

## 🔹 4. `clear()` – Liste **vollständig leeren**

```python
daten = [1, 2, 3]
daten.clear()
print(daten)  # []
```

- Liste bleibt erhalten, ist aber **leer**

---

## 🔹 5. `filter()` – Bedingte Entfernung

Beispiel: alle Zahlen **größer als 10** behalten

```python
werte = [5, 10, 15, 20]
neu = list(filter(lambda x: x > 10, werte))
print(neu)  # [15, 20]
```

---

## 🧠 Was ist wann sinnvoll?

| Methode     | Verwendung                              |
|-------------|------------------------------------------|
| `remove(x)` | Wenn du **nach Wert** löschen willst     |
| `pop(i)`    | Wenn du **nach Position** löschen willst |
| `del`       | Flexibel, auch für **Slicing & komplett** |
| `clear()`   | Leere die **ganze Liste**                |
| `filter()`  | **Bedingte** Löschung                    |

---

## 🚫 Vorsicht bei Loops

Nicht in Schleifen direkt `.remove()` verwenden:

```python
# Schlechte Praxis!
farben = ["rot", "blau", "rot"]
for f in farben:
    if f == "rot":
        farben.remove(f)

print(farben)  # ['blau'] – überspringt ein "rot"
```

> 🛠 Besser mit List Comprehension oder Kopie arbeiten.

---

## ✅ Zusammenfassung

| Methode         | Beschreibung                            |
|------------------|-----------------------------------------|
| `remove(x)`      | Entfernt erstes Vorkommen von `x`       |
| `pop(i)`         | Entfernt Element bei Index `i`          |
| `pop()`          | Entfernt letztes Element                |
| `del liste[i]`   | Entfernt Element an Index `i`           |
| `del liste[:]`   | Entfernt alle Elemente (auch `clear()`) |
| `clear()`        | Leert die Liste                         |
| `filter()`       | Neue Liste mit gewünschten Elementen     |

---

> 💡 Alle Methoden – außer `filter()` – **ändern die Liste direkt**.