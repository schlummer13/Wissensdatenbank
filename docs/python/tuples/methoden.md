# 🧰 Tuple-Methoden

Tuples sind **unveränderliche** (immutable) Datenstrukturen.  
Deshalb gibt es **nur zwei eingebaute Methoden**, die du direkt auf Tuples anwenden kannst:

- `count()` → Zählt, wie oft ein Element vorkommt  
- `index()` → Gibt die Position eines Elements zurück

---

## 🔢 `count()` – Vorkommen zählen

### 🔹 Zweck:
Zählt, wie oft ein bestimmter Wert im Tuple vorkommt.

```python
zahlen = (1, 2, 2, 3, 4, 2)

anzahl = zahlen.count(2)
print(anzahl)  # 3
```

> ✅ Gibt die Anzahl zurück  
> ❌ Gibt `0` zurück, wenn das Element **nicht** existiert

---

## 🔍 `index()` – Position eines Werts finden

### 🔹 Zweck:
Liefert den **Index** des **ersten** Vorkommens eines Werts.

```python
farben = ("rot", "grün", "blau", "grün")

pos = farben.index("grün")
print(pos)  # 1
```

> ⚠️ Wenn der Wert **nicht gefunden wird**, wirft Python einen `ValueError`.

---

## 🧠 Optional: Start- & Endposition angeben

`index()` kann mit zwei weiteren Parametern genutzt werden:

```python
zahlen = (1, 2, 3, 2, 4, 2)

# Suche ab Index 2
print(zahlen.index(2, 2))  # 3

# Suche zwischen Index 2 und 5
print(zahlen.index(2, 2, 5))  # 3
```

---

## 🔧 Methoden, die Tuples **nicht** haben:

| Methode       | Warum nicht verfügbar?                    |
|---------------|--------------------------------------------|
| `.append()`   | Nur für Listen – Tuple ist unveränderlich |
| `.remove()`   | Tuple kann nicht bearbeitet werden        |
| `.sort()`     | Tuple ist nicht veränderbar               |
| `.reverse()`  | Siehe oben                                |
| `.extend()`   | Nur für Listen                            |

Wenn du solche Änderungen brauchst → **in Liste umwandeln**:

```python
farben = ("rot", "grün", "blau")
farben_liste = list(farben)
farben_liste.append("gelb")
farben = tuple(farben_liste)
```

---

## ✅ Zusammenfassung

| Methode     | Beschreibung                           |
|-------------|----------------------------------------|
| `count(x)`  | Wie oft kommt `x` im Tuple vor?        |
| `index(x)`  | An welcher Stelle steht `x` im Tuple?  |

---

> 🧠 Tuples sind kompakt, schnell und stabil – ideal für feste Daten.  
> Brauchst du mehr Flexibilität → nutze Listen!