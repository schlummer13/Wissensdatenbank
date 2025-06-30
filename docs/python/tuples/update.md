# 🔄 Tuple "Update" (Ändern von Inhalten)

## ❗ Vorab: Tuples sind **immutable**

Ein **Tuple kann nach seiner Erstellung nicht direkt verändert werden**. Das heißt:

- Du kannst keine Elemente **hinzufügen**
- Du kannst keine Elemente **löschen**
- Du kannst keine Elemente **ersetzen**

```python
farben = ("rot", "grün", "blau")
farben[0] = "gelb"  # ❌ TypeError: 'tuple' object does not support item assignment
```

---

## 🧩 Aber wie kann man trotzdem „etwas ändern“?

Wenn du dennoch ein Tuple **verändern möchtest**, musst du es **in eine Liste umwandeln**, die Änderung vornehmen und danach **wieder ein Tuple erstellen**.

---

## 🔁 Beispiel: Wert ändern

```python
farben = ("rot", "grün", "blau")

# In Liste umwandeln
farben_liste = list(farben)

# Änderung vornehmen
farben_liste[0] = "gelb"

# Zurück in Tuple
farben = tuple(farben_liste)

print(farben)  # ('gelb', 'grün', 'blau')
```

---

## ➕ Beispiel: Element hinzufügen

```python
zahlen = (1, 2, 3)

zahlen_liste = list(zahlen)
zahlen_liste.append(4)

zahlen = tuple(zahlen_liste)
print(zahlen)  # (1, 2, 3, 4)
```

---

## ➖ Beispiel: Element entfernen

```python
tiere = ("Hund", "Katze", "Maus")

tiere_liste = list(tiere)
tiere_liste.remove("Katze")

tiere = tuple(tiere_liste)
print(tiere)  # ('Hund', 'Maus')
```

---

## 🧠 Alternativ: Neue Tuples zusammenfügen

Manchmal ist es praktischer, gleich **neue Tuples zu erzeugen**, statt zu "ändern":

```python
zahlen = (1, 2, 3)
zahlen_neu = zahlen + (4, 5)
print(zahlen_neu)  # (1, 2, 3, 4, 5)
```

> Du kannst Tuples **addieren** (konkatenieren) oder mit `*` vervielfachen.

---

## ✅ Zusammenfassung

| Aktion              | Tuple-Ansatz                                      |
|---------------------|---------------------------------------------------|
| Element ändern       | → in Liste umwandeln, ändern, zurück zu Tuple     |
| Element hinzufügen   | → `.append()` auf Liste, dann wieder Tuple        |
| Element löschen      | → `.remove()` auf Liste, dann wieder Tuple        |
| Tuple erweitern      | → `tuple1 + tuple2`                               |
| Tuple verdoppeln     | → `tuple * 2`                                     |

---

## 📌 Merksatz

> Tuples selbst ändern geht nicht –  
> aber mit einem kleinen **Trick über Listen** klappt’s trotzdem!