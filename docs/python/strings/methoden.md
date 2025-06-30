# 🧰 String-Methoden

Strings in Python sind **Objekte** und bringen eine Vielzahl an **integrierten Methoden** mit, mit denen man sie analysieren, umwandeln oder verändern kann.

Alle Methoden liefern **neue Strings zurück** (Strings sind **unveränderlich**!).

---

## 🔤 Groß-/Kleinschreibung

| Methode         | Beschreibung                            | Beispiel                          |
|-----------------|-------------------------------------------|-----------------------------------|
| `lower()`       | Alles klein                              | `"HALLO".lower()` → `"hallo"`     |
| `upper()`       | Alles groß                               | `"hallo".upper()` → `"HALLO"`     |
| `capitalize()`  | Erstes Zeichen groß                      | `"python".capitalize()` → `"Python"` |
| `title()`       | Jedes Wort mit Großbuchstaben           | `"hello world".title()` → `"Hello World"` |
| `swapcase()`    | Kehrt Groß-/Kleinschreibung um           | `"Hallo".swapcase()` → `"hALLO"`  |

---

## 🧪 Überprüfung (Boolean-Tests)

| Methode            | Bedeutung                              | Beispiel                     |
|--------------------|-----------------------------------------|------------------------------|
| `isalpha()`        | Nur Buchstaben?                         | `"Hallo".isalpha()` → `True` |
| `isdigit()`        | Nur Ziffern?                            | `"123".isdigit()` → `True`   |
| `isalnum()`        | Buchstaben oder Zahlen?                 | `"ABC123".isalnum()` → `True`|
| `isspace()`        | Nur Leerzeichen?                        | `"   ".isspace()` → `True`   |
| `isupper()`        | Nur Großbuchstaben?                     | `"HALLO".isupper()` → `True` |
| `islower()`        | Nur Kleinbuchstaben?                    | `"test".islower()` → `True`  |
| `istitle()`        | Titel-Schreibweise?                     | `"Hallo Welt".istitle()` → `True` |

---

## 🔍 Suchen & Finden

| Methode          | Beschreibung                          | Beispiel                             |
|------------------|-----------------------------------------|--------------------------------------|
| `find(sub)`      | Erste Position oder `-1`               | `"abcabc".find("b")` → `1`           |
| `rfind(sub)`     | Letzte Position oder `-1`             | `"abcabc".rfind("b")` → `4`          |
| `index(sub)`     | Wie `find()`, aber mit Fehler bei `-1`| `"abc".index("x")` → `ValueError`    |
| `count(sub)`     | Wie oft kommt `sub` vor?              | `"banana".count("a")` → `3`          |
| `startswith()`   | Beginnt mit?                          | `"Hallo".startswith("Ha")` → `True`  |
| `endswith()`     | Endet mit?                            | `"Hallo".endswith("lo")` → `True`    |

---

## 🔧 Ersetzen & Ändern

| Methode            | Bedeutung                              | Beispiel                              |
|--------------------|------------------------------------------|---------------------------------------|
| `replace(a, b)`    | Ersetze `a` durch `b`                    | `"Ich liebe JS".replace("JS", "Python")` |
| `strip()`          | Entfernt Leerzeichen (links + rechts)   | `"  Test  ".strip()` → `"Test"`       |
| `lstrip()`         | Entfernt links                          | `"  Text".lstrip()` → `"Text"`        |
| `rstrip()`         | Entfernt rechts                         | `"Text   ".rstrip()` → `"Text"`       |
| `zfill(n)`         | Füllt mit Nullen links auf              | `"7".zfill(3)` → `"007"`              |
| `center(n)`        | Zentriert String in `n` Zeichen         | `"Hi".center(6)` → `"  Hi  "`         |
| `ljust(n)`         | Links ausrichten                        | `"Hi".ljust(6, "-")` → `"Hi----"`     |
| `rjust(n)`         | Rechts ausrichten                       | `"Hi".rjust(6, "-")` → `"----Hi"`     |

---

## 🧱 Aufteilen & Zusammenfügen

| Methode              | Beschreibung                           | Beispiel                              |
|----------------------|------------------------------------------|---------------------------------------|
| `split()`            | Teilt bei Leerzeichen                   | `"a b c".split()` → `["a", "b", "c"]` |
| `split(",")`         | Teilt bei Trennzeichen                  | `"a,b,c".split(",")` → `["a", "b", "c"]` |
| `rsplit()`           | Von rechts teilen (gleich wie `split`)  |                                      |
| `partition(":")`     | Teilt in **3 Teile** (vor, Trenner, nach)| `"key:value".partition(":")` → `("key", ":", "value")` |
| `join(list)`         | Liste zu String verbinden               | `",".join(["a", "b"])` → `"a,b"`      |

---

## 🔐 Kodierung & Unicode

| Methode        | Beschreibung                      |
|----------------|-----------------------------------|
| `encode()`     | Wandelt in Byte-Objekt um         |
| `decode()`     | Wandelt Byte zurück zu String     |

```python
s = "Hallo"
b = s.encode("utf-8")
print(b)         # b'Hallo'
print(b.decode())  # Hallo
```

---

## 📘 Beispiel: Methoden in Aktion

```python
text = "   Python ist cool!  "
print(text.strip().upper().replace("COOL", "fantastisch"))
# → "PYTHON IST FANTASTISCH!"
```

---

## ✅ Zusammenfassung

| Bereich           | Typische Methoden                                |
|-------------------|--------------------------------------------------|
| Groß/Klein        | `lower()`, `upper()`, `capitalize()`             |
| Testen            | `isalpha()`, `isdigit()`, `isspace()`            |
| Suchen            | `find()`, `startswith()`, `count()`              |
| Bearbeiten        | `replace()`, `strip()`, `zfill()`, `center()`    |
| Trennen/Verbinden | `split()`, `join()`, `partition()`               |

---

> 🧠 Tipp: Probiere `dir("dein string")` in Python, um **alle verfügbaren Methoden** zu sehen!