# 🗂️ Zugriff auf Listen (Access)

Listen in Python sind **indexierte, geordnete Datenstrukturen**.  
Du kannst auf ihre Elemente gezielt zugreifen, sie lesen, verändern oder sogar mit **Slicing** Teilbereiche extrahieren.

---

## 📌 Indexbasierter Zugriff

Python verwendet **nullbasierte Indizierung**:  
Das **erste Element hat Index `0`**, das **letzte Element** Index `-1` (negativ rückwärts).

```python
früchte = ["Apfel", "Banane", "Kiwi", "Orange"]

print(früchte[0])   # Apfel
print(früchte[2])   # Kiwi
print(früchte[-1])  # Orange (letztes Element)
```

---

## 🧮 Negative Indizes

Mit negativen Indizes zählst du **vom Ende der Liste** zurück:

```python
print(früchte[-2])  # Kiwi
```

| Index | Element   |
|--------|------------|
| 0      | Apfel     |
| 1      | Banane    |
| 2      | Kiwi      |
| 3 / -1 | Orange    |

---

## ✍️ Werte ändern per Index

```python
früchte[1] = "Mango"
print(früchte)  # ["Apfel", "Mango", "Kiwi", "Orange"]
```

---

## 🚫 Zugriff außerhalb des Bereichs

```python
print(früchte[10])  # ❌ IndexError: list index out of range
```

➡️ Achte auf die Länge: `len(früchte)` hilft!

---

## 🧩 Slicing – Teilbereiche extrahieren

Mit dem **Slicing-Syntax** `liste[start:stop:step]` kannst du **Abschnitte** der Liste holen:

```python
zahlen = [10, 20, 30, 40, 50]
print(zahlen[1:4])    # [20, 30, 40]
print(zahlen[:3])     # [10, 20, 30]
print(zahlen[::2])    # [10, 30, 50] (jeder zweite)
print(zahlen[::-1])   # [50, 40, 30, 20, 10] (umgekehrt)
```

| Ausdruck         | Bedeutung                      |
|------------------|-------------------------------|
| `liste[a:b]`     | Von `a` (inkl.) bis `b` (exkl.) |
| `liste[:b]`      | Vom Anfang bis `b`             |
| `liste[a:]`      | Von `a` bis zum Ende           |
| `liste[::s]`     | Ganze Liste, alle `s` Schritte |
| `liste[::-1]`    | Ganze Liste rückwärts          |

---

## 🧠 Check: Ist Index gültig?

```python
index = 3
if index < len(früchte):
    print(früchte[index])
```

---

## ✅ Zusammenfassung

| Zugriff        | Beispiel             | Ergebnis            |
|----------------|----------------------|---------------------|
| Erstes Element | `liste[0]`           | erster Eintrag      |
| Letztes Element| `liste[-1]`          | letzter Eintrag     |
| Slicing        | `liste[1:4]`         | Teilbereich         |
| Rückwärts      | `liste[::-1]`        | umgekehrte Liste    |
| Ändern         | `liste[1] = "Neu"`   | überschreibt Element |

---

> 🧩 **Tipp**: Mit Slicing kannst du auch neue Listen auf Basis bestehender erzeugen – elegant & performant!