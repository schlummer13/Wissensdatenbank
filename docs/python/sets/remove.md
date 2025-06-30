# ❌ Set Elemente entfernen

In Python kannst du mit verschiedenen Methoden Elemente aus einem `set` löschen. Jede Methode hat ihre eigenen Besonderheiten.

---

## 🔹 `remove()` – Entfernt ein bestimmtes Element

```python
farben = {"rot", "blau", "grün"}
farben.remove("blau")
print(farben)  # {'rot', 'grün'}
```

- Entfernt **genau ein Element**
- ❗ Gibt einen **Fehler**, wenn das Element **nicht existiert**:

```python
farben.remove("gelb")  # ❌ KeyError!
```

---

## 🔸 `discard()` – Sicheres Entfernen

```python
farben = {"rot", "blau", "grün"}
farben.discard("blau")     # entfernt "blau"
farben.discard("gelb")     # kein Fehler
```

- Funktioniert wie `remove()`
- ✅ **Kein Fehler**, wenn das Element fehlt

---

## 🔻 `pop()` – Irgendein Element entfernen

```python
zahlen = {1, 2, 3}
entfernt = zahlen.pop()

print(entfernt)  # z. B. 1
print(zahlen)    # zwei übrige Zahlen
```

- Entfernt und gibt **ein beliebiges Element** zurück
- ❗ Reihenfolge **nicht vorhersehbar**
- ❗ Bei leerem Set → **KeyError**

---

## 🔄 `clear()` – Alles löschen

```python
farben = {"rot", "blau"}
farben.clear()

print(farben)  # set()
```

- Macht das Set **komplett leer**

---

## 🧪 Beispiel

```python
tiere = {"Katze", "Hund", "Maus"}

tiere.remove("Hund")
tiere.discard("Tiger")  # Kein Fehler
tiere.pop()             # Irgendein Tier
print(tiere)

tiere.clear()
print(tiere)  # → leeres Set
```

---

## 🧠 Vergleich der Methoden

| Methode     | Beschreibung                                | Fehler bei fehlendem Element? |
|-------------|---------------------------------------------|-------------------------------|
| `remove(x)` | Entfernt `x`, wirft Fehler wenn nicht da     | ❌ Ja (`KeyError`)            |
| `discard(x)`| Entfernt `x`, **ohne Fehler**                | ✅ Nein                       |
| `pop()`     | Entfernt **irgendein** Element               | ❌ Ja bei leerem Set          |
| `clear()`   | Entfernt **alle** Elemente                   | ✅ Nie                        |

---

## ✅ Zusammenfassung

| Ziel                                | Methode      |
|-------------------------------------|--------------|
| Sicher entfernen (ohne Fehler)      | `.discard(x)`|
| Genau entfernen (mit Fehlerwarnung) | `.remove(x)` |
| Irgendeines entfernen               | `.pop()`     |
| Alles löschen                       | `.clear()`   |

---

> 💡 Nutze `discard()`, wenn du nicht sicher bist, ob ein Element enthalten ist.  
> Vermeide `remove()` ohne Prüfung – es kann den Code abbrechen!