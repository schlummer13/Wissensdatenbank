# 🎨 Strings formatieren (`String Formatting`)

String-Formatierung bedeutet, **Daten in Texten dynamisch einzusetzen**, z. B. Zahlen, Namen oder Variablen. Python bietet dafür **mehrere flexible Methoden** – von klassisch bis modern.

---

## 🧰 Übersicht der Methoden

| Methode        | Beschreibung                      | Version         |
|----------------|-----------------------------------|------------------|
| `f-Strings`    | Moderne, empfohlene Methode        | Python ≥ 3.6     |
| `format()`     | Flexibel & weit verbreitet         | Python ≥ 2.7     |
| `%`-Format     | Alte C-Style-Syntax                | Python < 3.x     |

---

## ✅ Methode 1: `f-Strings` (empfohlen)

```python
name = "Florian"
alter = 32
print(f"Hallo, ich bin {name} und {alter} Jahre alt.")
```

- **Sehr lesbar**
- Unterstützt **Ausdrücke & Methoden**:

```python
zahl = 7.3456
print(f"Gerundet: {zahl:.2f}")  # Gerundet: 7.35
```

---

## ✅ Methode 2: `format()`

```python
template = "Hallo {}, du hast {} neue Nachrichten."
print(template.format("Anna", 3))
```

- **Platzhalter** werden durch `.format()` ersetzt
- Du kannst auch **Indizes oder Namen** verwenden:

```python
s = "{0} liebt {1}".format("Max", "Python")
print(s)

s = "{name} hat {anzahl} Punkte.".format(name="Lisa", anzahl=92)
```

---

## ✅ Methode 3: `%`-Format (älter)

```python
name = "Tim"
alter = 25
print("Name: %s, Alter: %d" % (name, alter))
```

| Kürzel | Typ              |
|--------|------------------|
| `%s`   | String            |
| `%d`   | Integer           |
| `%f`   | Float             |

⚠️ Wird **nicht mehr empfohlen** – nur noch in Altcode relevant.

---

## 🔢 Zahlen formatieren

```python
wert = 1234.56789
print(f"{wert:.2f}")       # 1234.57
print(f"{wert:,.2f}")      # 1,234.57 (mit Tausendertrennung)
print(f"{wert:10.2f}")     # rechtsbündig in 10 Zeichen
```

| Format      | Bedeutung                      |
|-------------|---------------------------------|
| `:.2f`      | 2 Nachkommastellen             |
| `:10.2f`    | Feldbreite 10, 2 Nachkommastellen |
| `:>10`      | rechtsbündig                    |
| `:<10`      | linksbündig                     |
| `:^10`      | zentriert                       |

---

## 💶 Beispiel mit Währung

```python
preis = 4.5
print(f"Preis: {preis:.2f} €")  # Preis: 4.50 €
```

---

## 🗂️ Tabellenformatierung

```python
daten = [
    ("Name", "Alter"),
    ("Anna", 22),
    ("Ben", 31),
    ("Clara", 27)
]

for name, alter in daten:
    print(f"{name:<10} | {alter:>3}")
```

➡️ Ergibt:

```
Name       | Age
Anna       |  22
Ben        |  31
Clara      |  27
```

---

## 🔍 Formatieren von Binär, Hex & Oktal

```python
zahl = 42
print(f"Binär: {zahl:b}")   # 101010
print(f"Hex: {zahl:x}")     # 2a
print(f"Oktal: {zahl:o}")   # 52
```

---

## ✨ Format mit Ausdrücken

```python
a = 5
b = 10
print(f"{a} + {b} = {a + b}")  # 5 + 10 = 15
```

---

## 🔐 Sicherheits-Tipp

Wenn du **Benutzereingaben** formatierst, vermeide:

```python
user_input = "{dangerous_code}"
print(f"{user_input}")  # ❌ potenzielle Sicherheitslücke
```

→ Nutze `str.format()` oder sichere Methoden.

---

## ✅ Zusammenfassung

| Methode     | Vorteil                            | Wann verwenden?           |
|-------------|-------------------------------------|----------------------------|
| `f""`       | Kurz, schnell, Ausdrucks-fähig      | ✅ Empfohlen (ab 3.6)       |
| `.format()` | Flexibel, kontrolliert              | Kompatibel, alt + neu      |
| `%`         | Altcode                             | ❌ Nicht mehr modern       |

---

> 🔧 Gute Formatierung macht deinen Code **lesbar, professionell und anpassbar**!