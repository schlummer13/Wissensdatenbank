# 🧾 Python – Syntaxübersicht

Eine kompakte Referenz zu den wichtigsten Regeln und Strukturen der Python-Sprache.

---

## 📌 Grundlegende Syntaxregeln

- **Einrückung** statt geschweifte Klammern `{}` zur Strukturierung von Codeblöcken  
- **Keine Semikolons** am Zeilenende notwendig  
- **Groß- und Kleinschreibung wichtig** (`Name` ≠ `name`)  
- **Kommentare** beginnen mit `#`  
- **Blöcke** (z. B. Schleifen, Bedingungen, Funktionen) enden **nicht** mit `end` o. ä.

---

## 🔤 Kommentare

```python
# Einzeiliger Kommentar

"""
Mehrzeiliger
Kommentar oder
Dokstring
"""
```

---

## 📏 Einrückung

```python
if True:
    print("Einrückung: 4 Leerzeichen empfohlen")
```

---

## 🟢 Anweisungen

- **Eine Anweisung pro Zeile**

```python
a = 1
b = 2
```

- **Mehrere Anweisungen in einer Zeile (nicht empfohlen)**

```python
a = 1; b = 2
```

---

## 📦 Blöcke mit Doppelpunkt `:`

```python
if x > 0:
    print("Positiv")
```

Gilt für:

- `if`, `elif`, `else`
- `for`, `while`
- `def`, `class`
- `try`, `except`, `finally`, `with`

---

## 🔧 Funktionsdefinition

```python
def funktion_name(parameter):
    pass
```

---

## 🧱 Klassendefinition

```python
class KlassenName:
    pass
```

---

## 🧮 Zuweisung

```python
a = 5
b, c = 1, 2
x = y = z = 0
```

---

## 📚 Import von Modulen

```python
import math
from math import pi
import os as betriebssystem
```

---

## 📦 Built-in Datentypen (nur Syntax)

```python
zahl = 5              # int
kommazahl = 5.3       # float
text = "Hallo"        # str
wahr = True           # bool
liste = [1, 2, 3]     # list
tupel = (1, 2)        # tuple
menge = {1, 2, 3}     # set
mapping = {"a": 1}    # dict
```

---

## ➕ Operatoren (nur Syntax)

```python
a + b    # Addition
a - b    # Subtraktion
a * b    # Multiplikation
a / b    # Division
a ** b   # Potenz
a // b   # Ganzzahldivision
a % b    # Modulo
```

---

## 🔁 Schleifen

```python
for i in range(5):
    pass

while bedingung:
    pass
```

---

## ❓ Bedingungen

```python
if x > 0:
    pass
elif x == 0:
    pass
else:
    pass
```

---

## 🔙 return, break, continue, pass

```python
return wert
break
continue
pass
```

---

## 🔗 Logische Operatoren

```python
and, or, not
```

---

## ❓ Ternärer Ausdruck

```python
status = "OK" if x > 0 else "Fehler"
```

---

## 📘 Weitere Syntaxelemente

```python
with open("datei.txt") as f:
    daten = f.read()

try:
    # etwas riskantes
except Exception as e:
    # Fehlerbehandlung
finally:
    # optional
```

---

## 🧠 Hinweis

Python folgt dem Prinzip:  
> „There should be one — and preferably only one — obvious way to do it.“  
(Quelle: The Zen of Python)