# 🧰 Liste: Methoden & Funktionen

Python-Listen (`list`) bieten viele **eingebaute Methoden**, mit denen man Inhalte **ändern**, **sortieren**, **suchen**, **löschen**, **hinzufügen** oder **kopieren** kann.

---

## 🔢 Übersicht der wichtigsten Methoden

| Methode           | Beschreibung                                 |
|-------------------|----------------------------------------------|
| `.append()`       | Element **hinten anhängen**                  |
| `.insert()`       | Element **an Position einfügen**             |
| `.extend()`       | Liste mit anderen Werten erweitern           |
| `.remove()`       | Element (nach Wert) löschen                  |
| `.pop()`          | Element **nach Index** löschen und zurückgeben |
| `.clear()`        | Liste komplett leeren                        |
| `.index()`        | Index eines Wertes ermitteln                 |
| `.count()`        | Wie oft kommt ein Wert vor?                  |
| `.sort()`         | Liste **in-place** sortieren                 |
| `.sorted()`       | Neue sortierte Liste zurückgeben             |
| `.reverse()`      | Liste umdrehen (in-place)                    |
| `.copy()`         | Flache Kopie erstellen                       |

---

## ➕ `.append()` – Am Ende anhängen

```python
zahlen = [1, 2]
zahlen.append(3)
print(zahlen)  # [1, 2, 3]
```

---

## 🔧 `.insert(index, wert)` – An Position einfügen

```python
farben = ["rot", "blau"]
farben.insert(1, "grün")
print(farben)  # ['rot', 'grün', 'blau']
```

---

## ➕ `.extend(iterable)` – Liste erweitern

```python
a = [1, 2]
b = [3, 4]
a.extend(b)
print(a)  # [1, 2, 3, 4]
```

---

## ❌ `.remove(wert)` – Erstes Vorkommen löschen

```python
tiere = ["Katze", "Hund", "Katze"]
tiere.remove("Katze")
print(tiere)  # ['Hund', 'Katze']
```

> ❗ Gibt Fehler, wenn Wert nicht existiert.

---

## 🎯 `.pop([index])` – Element löschen und zurückgeben

```python
zahlen = [5, 6, 7]
letzter = zahlen.pop()
print(letzter)  # 7
```

Mit Index:

```python
zahlen.pop(0)  # entfernt erstes Element
```

---

## 🧼 `.clear()` – Alles löschen

```python
daten = [1, 2, 3]
daten.clear()
print(daten)  # []
```

---

## 🔍 `.index(wert)` – Ersten Index ermitteln

```python
zahlen = [4, 5, 6]
i = zahlen.index(5)
print(i)  # 1
```

> ❗ Fehler, wenn Wert nicht existiert.

---

## 🔢 `.count(wert)` – Anzahl eines Wertes zählen

```python
werte = [1, 1, 2, 3, 1]
anzahl = werte.count(1)
print(anzahl)  # 3
```

---

## 📊 `.sort()` – Liste sortieren (ändert Original!)

```python
zahlen = [3, 1, 4]
zahlen.sort()
print(zahlen)  # [1, 3, 4]
```

Absteigend:

```python
zahlen.sort(reverse=True)
```

---

## 🆕 `sorted(liste)` – Neue sortierte Liste

```python
zahlen = [3, 1, 2]
neu = sorted(zahlen)
print(zahlen)  # [3, 1, 2]
print(neu)     # [1, 2, 3]
```

---

## 🔁 `.reverse()` – Reihenfolge umdrehen

```python
buchstaben = ["a", "b", "c"]
buchstaben.reverse()
print(buchstaben)  # ['c', 'b', 'a']
```

---

## 🧾 `.copy()` – Neue Kopie erstellen

```python
original = [1, 2, 3]
kopie = original.copy()
kopie.append(4)
print(original)  # [1, 2, 3]
```

---

## ✅ Zusammenfassung als Cheatsheet

| Aufgabe                        | Methode                          |
|--------------------------------|----------------------------------|
| Element anhängen               | `liste.append(wert)`             |
| Element an Position einfügen  | `liste.insert(index, wert)`      |
| Zwei Listen kombinieren       | `liste.extend(weitere_liste)`    |
| Element löschen (nach Wert)   | `liste.remove(wert)`             |
| Element löschen (Index)       | `liste.pop([index])`             |
| Liste komplett leeren         | `liste.clear()`                  |
| Vorkommen zählen              | `liste.count(wert)`              |
| Index finden                  | `liste.index(wert)`              |
| Liste sortieren (in-place)    | `liste.sort()`                   |
| Sortierte Kopie zurückgeben   | `sorted(liste)`                  |
| Reihenfolge umdrehen          | `liste.reverse()`                |
| Neue Kopie erstellen          | `liste.copy()`                   |

---

> 💡 Tipp: Viele dieser Methoden ändern die **Original-Liste**. Wenn du die alte Version behalten möchtest, nutze `.copy()` oder `sorted()`!