# 🔧 Python – Alle Operatoren einfach erklärt

Operatoren sind **Symbole**, mit denen du in Python **Berechnungen durchführen**, **Werte vergleichen**, **logische Entscheidungen treffen** und **Daten verknüpfen** kannst.

---

## ➕ Arithmetische Operatoren

| Operator | Beschreibung        | Beispiel         | Ergebnis         |
|----------|---------------------|------------------|------------------|
| `+`      | Addition             | `3 + 2`          | `5`              |
| `-`      | Subtraktion          | `5 - 1`          | `4`              |
| `*`      | Multiplikation       | `4 * 3`          | `12`             |
| `/`      | Division (float)     | `10 / 2`         | `5.0`            |
| `//`     | Ganzzahldivision     | `10 // 3`        | `3`              |
| `%`      | Modulo (Rest)        | `10 % 3`         | `1`              |
| `**`     | Potenzierung         | `2 ** 3`         | `8`              |

---

## 📏 Vergleichsoperatoren (Vergleichen Werte)

| Operator | Beschreibung           | Beispiel        | Ergebnis   |
|----------|------------------------|-----------------|------------|
| `==`     | Gleich                 | `3 == 3`        | `True`     |
| `!=`     | Ungleich               | `3 != 4`        | `True`     |
| `>`      | Größer                 | `5 > 2`         | `True`     |
| `<`      | Kleiner                | `1 < 3`         | `True`     |
| `>=`     | Größer oder gleich     | `4 >= 4`        | `True`     |
| `<=`     | Kleiner oder gleich    | `2 <= 5`        | `True`     |

---

## 🔗 Logische Operatoren (Bedingungen verknüpfen)

| Operator | Beschreibung              | Beispiel                 | Ergebnis   |
|----------|---------------------------|--------------------------|------------|
| `and`    | UND – beide müssen wahr   | `True and False`         | `False`    |
| `or`     | ODER – eins reicht        | `True or False`          | `True`     |
| `not`    | NICHT – kehrt um          | `not True`               | `False`    |

---

## 🧮 Zuweisungsoperatoren

| Operator | Bedeutung                 | Beispiel       | Wirkung             |
|----------|---------------------------|----------------|----------------------|
| `=`      | Zuweisung                 | `x = 10`       | Weist 10 zu          |
| `+=`     | Addieren & zuweisen       | `x += 2`       | `x = x + 2`          |
| `-=`     | Subtrahieren & zuweisen   | `x -= 1`       | `x = x - 1`          |
| `*=`     | Multiplizieren & zuweisen | `x *= 3`       | `x = x * 3`          |
| `/=`     | Dividieren & zuweisen     | `x /= 2`       | `x = x / 2`          |
| `//=`    | Ganzzahldivision          | `x //= 2`      | `x = x // 2`         |
| `%=`     | Modulo                    | `x %= 3`       | `x = x % 3`          |
| `**=`    | Potenzieren               | `x **= 2`      | `x = x ** 2`         |

---

## 🧵 Zeichenketten-Operatoren

| Operator | Beschreibung             | Beispiel                    | Ergebnis         |
|----------|--------------------------|-----------------------------|------------------|
| `+`      | Verknüpfen               | `"Hallo " + "Welt"`         | `"Hallo Welt"`   |
| `*`      | Wiederholen              | `"A" * 3`                   | `"AAA"`          |

---

## 🔍 Identitätsoperatoren

| Operator | Beschreibung                          | Beispiel           | Ergebnis |
|----------|---------------------------------------|--------------------|----------|
| `is`     | Ob zwei Namen **dasselbe Objekt** zeigen | `a is b`         | `True/False` |
| `is not` | Gegenteil                             | `a is not b`       | `True/False` |

```python
a = [1, 2]
b = a
c = [1, 2]
a is b      # True (gleiche Referenz)
a is c      # False (andere Objekte mit gleichem Inhalt)
```

---

## 📌 Mitgliedsoperatoren

| Operator | Beschreibung                    | Beispiel         | Ergebnis |
|----------|---------------------------------|------------------|----------|
| `in`     | Ist Element enthalten?          | `"a" in "abc"`   | `True`   |
| `not in` | Ist Element NICHT enthalten?    | `"x" not in "abc"`| `True`  |

---

## ❓ Ternärer Operator (Konditional)

```python
x = 18
status = "volljährig" if x >= 18 else "minderjährig"
```

- Kompakte `if/else`-Alternative

---

## 🧠 Bitweise Operatoren (für Integer, auf Binärebene)

| Operator | Beschreibung     | Beispiel      | Ergebnis |
|----------|------------------|---------------|----------|
| `&`      | Bitweises UND     | `5 & 3` → 1   | `0b101 & 0b011` |
| `|`      | Bitweises ODER    | `5 | 3` → 7   | `0b111`        |
| `^`      | Exklusives ODER   | `5 ^ 3` → 6   | `0b110`        |
| `~`      | Bitweises NICHT   | `~5` → -6     |              |
| `<<`     | Linksverschiebung | `5 << 1` → 10 |              |
| `>>`     | Rechtsverschiebung| `5 >> 1` → 2  |              |

---

## 🧪 Typprüfung mit `type()` & `isinstance()`

```python
type(5) == int
isinstance("Hallo", str)
```

---

## ✅ Zusammenfassung nach Gruppen

| Kategorie      | Beispiele                    |
|----------------|------------------------------|
| Arithmetisch   | `+`, `-`, `*`, `/`, `//`, `%`, `**` |
| Vergleich      | `==`, `!=`, `>`, `<`, `>=`, `<=`    |
| Logisch        | `and`, `or`, `not`           |
| Zuweisung      | `=`, `+=`, `*=`, etc.        |
| Identität      | `is`, `is not`               |
| Mitgliedschaft | `in`, `not in`               |
| Ternär         | `x if cond else y`           |
| Bitweise       | `&`, `|`, `^`, `~`, `<<`, `>>` |

---

## 📘 Tipp

Nutze `help(operator)` oder das [`operator`](https://docs.python.org/3/library/operator.html)-Modul für noch mehr Kontrolle und Funktionalität, besonders bei benutzerdefinierten Objekten.