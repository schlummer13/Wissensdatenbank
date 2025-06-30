# ➕ Set Elemente hinzufügen

Ein Set in Python speichert **einzigartige** Elemente. Um neue Einträge hinzuzufügen, nutzt du die Methode **`.add()`**.

---

## 🔹 `add()` – Ein Element hinzufügen

```python
farben = {"rot", "blau"}
farben.add("grün")

print(farben)  # {'rot', 'blau', 'grün'}
```

- Fügt **genau ein** neues Element zum Set hinzu
- Wenn der Wert **schon vorhanden ist**, passiert **nichts**

```python
farben.add("rot")
print(farben)  # {'rot', 'blau', 'grün'} → kein Duplikat!
```

---

## 🔸 `update()` – Mehrere Werte hinzufügen

Wenn du **mehrere** Elemente hinzufügen möchtest, nutze `update()`:

```python
zahlen = {1, 2}
zahlen.update([3, 4, 5])
print(zahlen)  # {1, 2, 3, 4, 5}
```

- Akzeptiert jede **iterierbare Struktur** (z. B. Liste, Tuple, Set, String)

```python
zahlen.update((6, 7))
zahlen.update("89")  # Achtung: einzelne Zeichen!
```

---

## 🧠 `add()` vs `update()` – Vergleich

| Methode   | Was wird hinzugefügt?             | Beispiel                 |
|-----------|------------------------------------|--------------------------|
| `add(x)`  | Ein einzelner Wert                 | `mein_set.add("Hallo")` |
| `update(x)` | Mehrere Werte (iterierbar)       | `mein_set.update(["A", "B"])` |

---

## 🧪 Beispiele

```python
tiere = {"Katze", "Hund"}
tiere.add("Maus")
tiere.update(["Fisch", "Vogel"])
print(tiere)
# Ausgabe: {'Hund', 'Katze', 'Maus', 'Fisch', 'Vogel'}
```

---

## ⚠️ Was **nicht** geht:

```python
mein_set = {1, 2, 3}
mein_set.add([4, 5])  # ❌ TypeError: Listen sind nicht hashbar
```

- **Unveränderliche Typen** (wie Zahlen, Strings, Tuples) sind erlaubt
- **Veränderliche Typen** (z. B. Listen, Dictionaries) **nicht**

---

## ✅ Zusammenfassung

| Ziel                           | Methode        |
|--------------------------------|----------------|
| Ein Wert                       | `.add(wert)`   |
| Mehrere Werte                  | `.update(iterable)` |
| Doppelte verhindern            | Automatisch durch Set |
| Fehler bei Liste als Element   | Ja – Listen sind nicht erlaubt |

---

> 💡 Nutze `add()` für einzelne Elemente und `update()` für Listen, Tuples oder andere Sets.  
> Sets sind **effizient** und verhindern automatisch **Doppelungen** – ideal für eindeutige Datensammlungen!