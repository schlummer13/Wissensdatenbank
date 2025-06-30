# 📦 Python – Alle Datentypen im Überblick

Python ist **dynamisch typisiert**, das heißt: Du musst den Datentyp nicht angeben – Python erkennt ihn automatisch. Trotzdem ist es wichtig, alle Typen und ihre Eigenschaften zu kennen.

---

## 🔢 1. Zahlentypen (Numeric Types)

### 🧮 `int` – Ganzzahlen

```python
a = 42
b = -7
```

- Unbegrenzt groß
- Kein Dezimalpunkt

---

### 📐 `float` – Gleitkommazahlen

```python
pi = 3.1415
```

- Enthält Dezimalpunkt
- Genauigkeit kann begrenzt sein

---

### 🔍 `complex` – Komplexe Zahlen

```python
z = 2 + 3j
```

- Mathematische komplexe Zahlen mit `j` (nicht `i`)
- Teile: `.real` und `.imag`

---

## 🔤 2. Texttyp

### 📝 `str` – Zeichenketten (Strings)

```python
text = "Hallo Welt"
```

- In `'` oder `"` oder `"""` (mehrzeilig)
- Unveränderlich (immutable)

---

## ✅ 3. Boolescher Typ

### 🔘 `bool`

```python
wahr = True
falsch = False
```

- Ergebnis von Vergleichen (`==`, `!=`, etc.)
- Intern `True == 1`, `False == 0`

---

## 📚 4. Sequenzen (geordnete Sammlungen)

### 📦 `list` – Liste

```python
zahlen = [1, 2, 3]
```

- Verändertbar (mutable)
- Elemente beliebiger Typen
- Methoden: `.append()`, `.remove()`, `.sort()`, etc.

---

### 🧱 `tuple` – Tupel

```python
koordinaten = (10, 20)
```

- Unveränderlich (immutable)
- Nützlich für feste Datengruppen
- Auch als Rückgabewert mehrerer Elemente

---

### 🆔 `range` – Zahlenbereich

```python
r = range(5)  # 0 bis 4
```

- Speicherfreundlich
- Häufig in Schleifen

---

### 🧵 `str` – Zeichenkette

Bereits oben erwähnt – gehört ebenfalls zu den Sequenzen!

---

## 🔑 5. Mapping

### 🧭 `dict` – Wörterbuch

```python
person = {"name": "Anna", "alter": 30}
```

- Schlüssel–Wert-Paare
- Schlüssel: einzigartig, meist `str` oder `int`
- Methoden: `.get()`, `.keys()`, `.values()`

---

## 📌 6. Mengen

### 🎯 `set` – Menge

```python
farben = {"rot", "blau", "grün"}
```

- Keine Duplikate
- Ungeordnet
- Methoden: `.add()`, `.remove()`, Mengenoperationen

---

### 🧪 `frozenset` – Unveränderliche Menge

```python
f = frozenset([1, 2, 3])
```

- Wie `set`, aber **immutable**

---

## 🧩 7. Binärtypen

### 📦 `bytes` – Byte-Sequenz (unveränderlich)

```python
daten = b"Hallo"
```

### 🔧 `bytearray` – Verändertbare Byte-Sequenz

```python
daten = bytearray([65, 66, 67])
```

### 🔍 `memoryview` – Speicheransicht

```python
mv = memoryview(b"abc")
```

- Zugriff auf Pufferdaten (z. B. für große Binärdateien)

---

## 🚫 8. `NoneType`

### 🅾️ `None`

```python
nichts = None
```

- Bedeutet: Kein Wert vorhanden
- Wird oft als Rückgabewert verwendet, wenn Funktion nichts zurückgibt

---

## 📊 9. Typenprüfung

```python
type(x)         # Gibt den Typ zurück
isinstance(x, list)  # Prüft, ob x eine Liste ist
```

---

## 🧠 Zusammenfassung (Kurzform)

| Typ         | Beschreibung                             |
|-------------|------------------------------------------|
| `int`       | Ganze Zahl                               |
| `float`     | Gleitkommazahl                           |
| `complex`   | Komplexe Zahl                            |
| `str`       | Zeichenkette                             |
| `bool`      | Wahr/Falsch                              |
| `list`      | Veränderliste                            |
| `tuple`     | Unveränderliste                          |
| `range`     | Bereich von Zahlen                       |
| `dict`      | Schlüssel–Wert-Paare                     |
| `set`       | Menge ohne Duplikate                     |
| `frozenset` | Unveränderliche Menge                    |
| `bytes`     | Unveränderlicher Binärtyp                |
| `bytearray` | Veränderl. Binärtyp                      |
| `memoryview`| Speicherzugriff auf Byte-Daten          |
| `NoneType`  | Repräsentiert "kein Wert" (`None`)       |

---

## 📚 Tipp

Verwende die Funktion `type()` zur schnellen Typprüfung:

```python
print(type("Test"))  # <class 'str'>
```