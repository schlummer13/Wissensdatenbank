# 📦 Einführung in Tuple (Tupel)

Ein **Tuple** ist eine **geordnete, unveränderbare (immutable)** Sammlung von Werten. Es ist vergleichbar mit einer Liste – aber **einmal erstellt, kann ein Tuple nicht verändert werden** (d.h. keine neuen Elemente hinzufügen, entfernen oder ändern).

> ✅ Gut geeignet für **konstante Daten** oder wenn **Datensicherheit** gewünscht ist.

---

## 🧩 Tuple erstellen

```python
# Mit Klammern
farben = ("rot", "grün", "blau")

# Ohne Klammern (optional)
zahlen = 1, 2, 3

# Einzelwert-Tuple (Komma notwendig!)
einzeltupel = ("eins",)
```

> ❗ Ohne das **Komma** wäre es nur ein String oder eine Zahl – kein Tuple!

---

## 🔍 Tuple ausgeben und prüfen

```python
print(farben[0])       # rot
print(len(farben))     # 3
print("grün" in farben) # True
```

---

## 🧠 Warum Tuples?

| Vorteil                      | Beschreibung                             |
|------------------------------|------------------------------------------|
| ✅ Unveränderlich             | Schutz vor ungewollter Modifikation      |
| ✅ Schnell & speichereffizient| Besser für große Datenmengen             |
| ✅ Hashbar                   | Kann als Schlüssel in Dictionaries dienen |
| ✅ Klarheit im Code          | "Das ist ein fester Datensatz"           |

---

## 🔄 Tuple zu Liste (änderbar machen)

```python
zahlen = (1, 2, 3)
zahlen_liste = list(zahlen)
zahlen_liste.append(4)
zahlen = tuple(zahlen_liste)
print(zahlen)  # (1, 2, 3, 4)
```

---

## 🔁 Tuple durchlaufen

```python
farben = ("rot", "grün", "blau")

for farbe in farben:
    print(farbe)
```

---

## 🧪 Tuple Entpacken (Unpacking)

```python
person = ("Anna", 30, "Entwicklerin")

name, alter, beruf = person

print(name)   # Anna
print(alter)  # 30
```

> 💡 Du kannst auch `*` verwenden:

```python
a, *b = (1, 2, 3, 4)
print(a)  # 1
print(b)  # [2, 3, 4]
```

---

## 🧾 Häufige Methoden

| Methode/Funktion | Beschreibung                        |
|------------------|-------------------------------------|
| `len(t)`         | Länge ermitteln                     |
| `t.count(x)`     | Anzahl von x zählen                 |
| `t.index(x)`     | Index von x finden                  |
| `in`             | Prüfen ob Element enthalten ist     |
| `for x in t`     | Iteration über Elemente             |

```python
zahlen = (1, 2, 2, 3)
print(zahlen.count(2))  # 2
print(zahlen.index(3))  # 3
```

---

## 📚 Tuple vs. Liste – Unterschiede

| Eigenschaft      | Liste (`list`)       | Tuple (`tuple`)     |
|------------------|----------------------|----------------------|
| Änderbar         | ✅ Ja                 | ❌ Nein               |
| Syntax           | `[1, 2, 3]`          | `(1, 2, 3)`          |
| Performance      | 🐢 langsamer          | ⚡ schneller          |
| Speicherplatz    | 🧠 mehr                | 💾 weniger            |
| Hashbar          | ❌ Nein               | ✅ Ja (wenn Inhalt hashbar) |

---

## ✅ Wann Tuple verwenden?

- Wenn Daten **fest** und **unveränderlich** sind  
- Als **Rückgabewerte** von Funktionen mit mehreren Werten  
- Wenn du **Leistung** und **Datensicherheit** brauchst  
- Für **koordinierte Daten** (z. B. `(x, y)` Punkte)

---

## 🧪 Beispiel – Rückgabe mit mehreren Werten

```python
def teile(x, y):
    return x // y, x % y

quotient, rest = teile(10, 3)
print(quotient, rest)  # 3 1
```

---

> 🎯 Fazit:  
> Tuples sind **leicht, sicher, schnell** – und perfekt für Daten, die sich nicht verändern sollen.