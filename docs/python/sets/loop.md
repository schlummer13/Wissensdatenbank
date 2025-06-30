# 🔁 Sets iterieren (Loop)

Ein `set` enthält **ungeordnete, eindeutige Elemente**. Um auf jedes Element zuzugreifen, kann man ganz einfach **Schleifen** verwenden.

---

## 🔹 `for`-Schleife über ein Set

```python
farben = {"rot", "grün", "blau"}

for farbe in farben:
    print(farbe)
```

- Durchläuft **jedes Element einmal**
- Reihenfolge ist **nicht festgelegt** (da Sets ungeordnet sind)

### 🔍 Beispiel-Ausgabe:
```
grün
blau
rot
```
> Hinweis: Die Reihenfolge kann sich bei jedem Durchlauf ändern.

---

## 🧠 Iteration mit Bedingungen

```python
farben = {"rot", "blau", "gelb"}

for farbe in farben:
    if "l" in farbe:
        print(f"{farbe} enthält den Buchstaben 'l'")
```

---

## 🔁 Iteration mit `enumerate()`

```python
farben = {"rot", "grün", "blau"}

for index, wert in enumerate(farben):
    print(f"{index}: {wert}")
```

- `enumerate()` gibt zusätzlich den **Index** zurück
- Die Reihenfolge bleibt **ungeordnet**, aber du bekommst Positionsnummern

---

## 🔄 Kombinieren mit `sorted()`

Wenn du die Werte **sortiert** durchlaufen willst:

```python
zahlen = {5, 3, 9, 1}

for z in sorted(zahlen):
    print(z)
```

➡️ Gibt aus:
```
1
3
5
9
```

---

## 🔁 Zugriff in einer `while`-Schleife (indirekt)

Man kann Sets in Listen umwandeln:

```python
tiere = {"Hund", "Katze", "Maus"}
liste = list(tiere)

i = 0
while i < len(liste):
    print(liste[i])
    i += 1
```

---

## 🧪 Beispiel: Zählen, wie oft ein Buchstabe in Set-Wörtern vorkommt

```python
wörter = {"apfel", "banane", "birne"}
zähler = 0

for wort in wörter:
    if "e" in wort:
        zähler += 1

print(f"In {zähler} Wörtern ist ein 'e' enthalten.")
```

---

## ✅ Zusammenfassung

| Technik               | Beschreibung                            |
|------------------------|------------------------------------------|
| `for element in set`  | Durchläuft jedes Element im Set          |
| `enumerate(set)`      | Liefert zusätzlich eine Indexnummer      |
| `sorted(set)`         | Gibt Elemente **sortiert** zurück        |
| `while` mit `list()`  | Indirekter Zugriff über Umwandlung       |

---

> 💡 Obwohl Sets keine Reihenfolge haben, lassen sie sich einfach mit `for` durchlaufen – ideal für Duplikat-freie Listen!