# ✏️ Strings verändern (String Modification)

Strings in Python sind **unveränderlich (immutable)** – das bedeutet:  
Du kannst den ursprünglichen String **nicht direkt ändern**, aber du kannst durch **Methoden** einen **neuen veränderten String** zurückbekommen.

---

## 🧱 Grundprinzip

```python
text = "hallo"
text = text.upper()
print(text)  # HALLO
```

> ✅ Methoden geben **immer neue Strings zurück**

---

## 🔤 Groß-/Kleinschreibung

| Methode        | Beschreibung                            |
|----------------|-------------------------------------------|
| `lower()`      | Alles klein                              |
| `upper()`      | Alles groß                               |
| `capitalize()` | Erstes Zeichen groß, Rest klein          |
| `title()`      | Jedes Wort groß                          |
| `swapcase()`   | Groß ↔ Klein                             |

```python
s = "heLLo WorLD"
print(s.lower())      # hello world
print(s.upper())      # HELLO WORLD
print(s.capitalize()) # Hello world
print(s.title())      # Hello World
print(s.swapcase())   # HEllO wORld
```

---

## ✂️ Entfernen & Ersetzen

| Methode      | Beschreibung                            |
|--------------|-------------------------------------------|
| `strip()`    | Entfernt Leerzeichen (oder andere Zeichen) vorne & hinten |
| `lstrip()`   | Nur links entfernen                      |
| `rstrip()`   | Nur rechts entfernen                     |
| `replace()`  | Ersetzt Teilstring durch anderen         |

```python
t = "  Python  "
print(t.strip())     # "Python"
print(t.replace("y", "i"))  # "Pithon"
```

---

## 🔎 Suchen & Finden

| Methode         | Beschreibung                                |
|------------------|---------------------------------------------|
| `find()`         | Gibt Index des ersten Vorkommens zurück (oder -1) |
| `rfind()`        | Letztes Vorkommen                          |
| `index()`        | Wie `find()`, aber Fehler bei Nichtfinden |
| `in`             | Gibt `True` zurück, wenn enthalten         |

```python
s = "programmieren"
print(s.find("m"))     # 6
print(s.rfind("m"))    # 7
print("gram" in s)     # True
```

---

## 🧩 Ersetzen mit `replace()`

```python
text = "Das ist gut. Das ist schön."
neu = text.replace("Das", "Es")
print(neu)  # "Es ist gut. Es ist schön."
```

---

## ✂️ Aufteilen & Zusammenfügen

| Methode         | Beschreibung                             |
|------------------|-------------------------------------------|
| `split()`        | Teilt String in Liste (Standard: Leerzeichen) |
| `rsplit()`       | Von rechts aufteilen                     |
| `join()`         | Liste von Strings zu einem String verbinden |

```python
satz = "eins zwei drei"
liste = satz.split()
print(liste)  # ['eins', 'zwei', 'drei']

neu = "-".join(liste)
print(neu)  # "eins-zwei-drei"
```

---

## 🔐 Formatieren

| Methode             | Beschreibung                         |
|----------------------|--------------------------------------|
| `format()`           | Einfügen von Werten                  |
| `f""` (f-Strings)    | Kurzschreibweise ab Python 3.6       |

```python
name = "Florian"
alter = 32

# klassisch
print("Name: {}, Alter: {}".format(name, alter))

# modern
print(f"Name: {name}, Alter: {alter}")
```

---

## 📊 Ausrichten & Auffüllen

| Methode         | Beispiel                       |
|------------------|--------------------------------|
| `center(w)`      | Zentrieren                     |
| `ljust(w)`       | Links ausrichten               |
| `rjust(w)`       | Rechts ausrichten              |
| `zfill(w)`       | Mit Nullen auffüllen           |

```python
s = "42"
print(s.zfill(5))    # 00042
print(s.rjust(5))    # "   42"
print(s.center(7))   # "  42   "
```

---

## 🧪 Validierung & Prüfung

| Methode         | Beschreibung                       |
|------------------|------------------------------------|
| `isalnum()`      | nur Buchstaben/Zahlen?            |
| `isalpha()`      | nur Buchstaben?                   |
| `isdigit()`      | nur Ziffern?                      |
| `isspace()`      | nur Leerzeichen?                  |
| `startswith()`   | beginnt mit…?                     |
| `endswith()`     | endet mit…?                       |

```python
code = "AB123"
print(code.isalnum())     # True
print(code.startswith("AB"))  # True
```

---

## 🔁 Wiederholen & Multiplizieren

```python
print("Na" * 3)  # "NaNaNa"
```

---

## ✅ Zusammenfassung

| Bereich              | Methode-Beispiele                          |
|----------------------|---------------------------------------------|
| Groß/Klein           | `lower()`, `upper()`, `title()`            |
| Entfernen/Ersetzen   | `strip()`, `replace()`, `split()`          |
| Prüfen/Suchen        | `find()`, `startswith()`, `in`             |
| Formatieren          | `format()`, `f""`, `zfill()`, `rjust()`     |
| Kombinieren          | `join()`, `*`                               |
