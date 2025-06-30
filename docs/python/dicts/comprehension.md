# 🧠 Dictionary Comprehension

**Dictionary Comprehension** ist eine kompakte Methode, um ein Dictionary **in einer einzigen Zeile** zu erstellen oder umzuwandeln – elegant, übersichtlich und oft sehr performant.

---

## 📦 Was ist Dictionary Comprehension?

Mit Dictionary Comprehension kannst du aus einer **Liste, einem anderen Dictionary oder beliebigen iterierbaren Objekten** dynamisch ein neues Dictionary erzeugen.

🧱 Grundstruktur:

```python
{schlüssel: wert for element in iterable}
```

---

## ✅ Einfaches Beispiel

```python
zahlen = [1, 2, 3, 4]

quadrate = {x: x**2 for x in zahlen}
print(quadrate)  # {1: 1, 2: 4, 3: 9, 4: 16}
```

➡️ Jeder Wert aus `zahlen` wird Schlüssel und das Quadrat der Wert.

---

## 🧪 Mit Bedingung (if-Filter)

```python
gerade_quadrate = {x: x**2 for x in zahlen if x % 2 == 0}
print(gerade_quadrate)  # {2: 4, 4: 16}
```

➡️ Nur gerade Zahlen werden berücksichtigt.

---

## 🔁 Aus anderer Quelle (z. B. Liste von Tupeln)

```python
paare = [("a", 1), ("b", 2), ("c", 3)]

neues_dict = {key: value for (key, value) in paare}
# {'a': 1, 'b': 2, 'c': 3}
```

---

## 🔁 Umkehren eines Dictionaries

```python
original = {"x": 10, "y": 20}

umgekehrt = {v: k for k, v in original.items()}
# {10: 'x', 20: 'y'}
```

---

## 🔧 Mit `enumerate()`

```python
namen = ["Anna", "Ben", "Clara"]

indexiert = {i: name for i, name in enumerate(namen)}
# {0: 'Anna', 1: 'Ben', 2: 'Clara'}
```

---

## 🔁 Doppelte Schleifen

```python
kombinationen = {(x, y): x * y for x in range(1, 3) for y in range(1, 4)}
# {(1, 1): 1, (1, 2): 2, (1, 3): 3, (2, 1): 2, (2, 2): 4, (2, 3): 6}
```

➡️ Du kannst mehrere Schleifen in einem Dictionary Comprehension nutzen!

---

## 🔎 Mit `if...else` im Ausdruck

```python
status = {x: ("gerade" if x % 2 == 0 else "ungerade") for x in range(5)}
# {0: 'gerade', 1: 'ungerade', 2: 'gerade', 3: 'ungerade', 4: 'gerade'}
```

---

## ✅ Zusammenfassung

| Technik                          | Beispiel                                  |
|----------------------------------|-------------------------------------------|
| Basis-Comprehension              | `{x: x**2 for x in liste}`                |
| Mit Filter (`if`)                | `{x: x for x in liste if x > 0}`          |
| Mit `enumerate()`                | `{i: val for i, val in enumerate(...)}`   |
| Paare aus Liste                  | `{k: v for (k, v) in tupel_liste}`        |
| Umkehren                         | `{v: k for k, v in dict.items()}`         |
| Mit `if...else` im Ausdruck     | `{x: "typ" if x > 0 else "leer" ...}`     |

---

> 🧠 Dictionary Comprehension ist ideal, um **effizient, kompakt und leserlich** neue Dictionaries zu erzeugen – besonders für Transformationen oder Filterungen.