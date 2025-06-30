# 🧾 Python Typing – Typhinweise und Typisierung

Ab Python 3.5 kannst du mit **Type Hints** den **Datentyp von Variablen, Parametern und Rückgabewerten** angeben. Python prüft diese **nicht zur Laufzeit**, aber sie verbessern die Lesbarkeit und ermöglichen Tools wie **mypy**, **Pyright** oder **VS Code** präzisere Fehlermeldungen und Autovervollständigung.

---

## 🔤 Einfache Typhinweise

```python
def begruessung(name: str) -> str:
    return "Hallo " + name
```

- `name: str` → Eingabe muss ein `str` sein
- `-> str` → Rückgabewert ist ein `str`

---

## 📦 Typen für Variablen

```python
x: int = 42
pi: float = 3.14
ist_aktiv: bool = True
text: str = "Hallo"
```

---

## 🧱 Built-in Typen

| Typ      | Beschreibung               |
|----------|----------------------------|
| `int`    | Ganze Zahl                 |
| `float`  | Gleitkommazahl             |
| `bool`   | Wahr/Falsch                |
| `str`    | Zeichenkette               |
| `bytes`  | Byte-Daten                 |

---

## 📚 Collection-Typen

```python
from typing import List, Dict, Tuple, Set

namen: List[str] = ["Anna", "Ben"]
punkte: Dict[str, int] = {"Anna": 5, "Ben": 7}
koordinaten: Tuple[int, int] = (10, 20)
farben: Set[str] = {"rot", "blau"}
```

---

## 🔄 Optional & Union

```python
from typing import Optional, Union

def lade_benutzer(id: int) -> Optional[str]:
    if id == 1:
        return "Admin"
    return None

def parse_eingabe(e: Union[str, int]) -> str:
    return str(e)
```

- `Optional[str]` = `str` oder `None`
- `Union[A, B]` = entweder A oder B

---

## 🧩 Any – "beliebiger Typ"

```python
from typing import Any

def debug(wert: Any) -> None:
    print(wert)
```

- Kein Typ-Check durch Tools – universell

---

## ⚙️ Callable – Funktionen typisieren

```python
from typing import Callable

def verarbeite(callback: Callable[[str], int]) -> int:
    return callback("Test")
```

- `[str]` = erwartet einen `str` als Eingabe
- `int` = Rückgabewert der Funktion

---

## 🧮 Type Alias

```python
from typing import Tuple

RGB = Tuple[int, int, int]
farbe: RGB = (255, 0, 0)
```

- Kürzel für komplexe Typen

---

## 🧪 Typed Dict (strukturiertes Dictionary)

```python
from typing import TypedDict

class Person(TypedDict):
    name: str
    alter: int

p: Person = {"name": "Florian", "alter": 32}
```

---

## 🧱 Typisierung mit `dataclasses`

```python
from dataclasses import dataclass

@dataclass
class Produkt:
    id: int
    name: str
    preis: float

artikel = Produkt(1, "Buch", 9.99)
```

- Automatisch erzeugter Konstruktor mit Typprüfung
- Sehr gut geeignet für strukturierte Daten

---

## 🧠 Vorteile von Typing

- **Lesbarkeit**: Du siehst sofort, was erwartet wird
- **Wartbarkeit**: Klare Verträge zwischen Funktionen
- **Tooling**: Editor zeigt Fehler, bevor du startest
- **Dokumentation**: Weniger Kommentare nötig

---

## 📚 Nützliche Typing-Module

| Modul              | Beschreibung                             |
|--------------------|------------------------------------------|
| `typing`           | Standard-Typen (List, Union, Optional…)  |
| `typing_extensions`| Zusätzliche Typen (z. B. `Literal`)       |
| `collections.abc`  | Neue Schreibweise: `list` statt `List` (ab 3.9) |

---

## ✅ Modernere Schreibweise (ab Python 3.9+)

```python
def combine(texts: list[str]) -> str:
    return ", ".join(texts)
```

- Keine `from typing import List` mehr nötig
- Nutzt eingebaute Typnamen direkt

---

## 📘 Fazit

Python bleibt dynamisch, aber mit **Type Hints** bekommst du die Vorteile von statischer Typisierung – ohne Zwang. Sie sind **optional, aber empfehlenswert**, vor allem bei großen Projekten.