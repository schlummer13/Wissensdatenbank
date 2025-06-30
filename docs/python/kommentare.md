# 💬 Python – Kommentare

Kommentare dienen dazu, Code verständlicher zu machen. Sie werden vom Python-Interpreter **ignoriert** und beeinflussen die Programmlogik nicht.

---

## 🧩 Einzeilige Kommentare

Beginnen mit dem **Hash-Zeichen** `#` – alles dahinter auf der gleichen Zeile ist ein Kommentar.

```python
# Das ist ein Kommentar
x = 42  # Kommentar am Zeilenende
```

✅ Gut für kurze Hinweise oder Dokumentation direkt neben dem Code.

---

## 🧩 Mehrzeilige Kommentare (Dokstrings)

Python kennt **formal keine echten mehrzeiligen Kommentare**. Aber du kannst dafür **mehrzeilige Strings** (`""" """` oder `''' '''`) verwenden. Diese werden zwar technisch als String behandelt, aber wenn sie **nicht zugewiesen** oder **nicht als Docstring verwendet** werden, ignoriert sie der Interpreter.

```python
"""
Das ist ein mehrzeiliger
Kommentar-ähnlicher Block.
Er wird ignoriert, wenn er nicht benutzt wird.
"""
```

Alternativ:

```python
'''
Mehrzeiliger
"Kommentar"
mit einfachen Hochkommas
'''
```

---

## 🧠 Docstrings (Dokumentationsstrings)

Wenn du einen solchen mehrzeiligen String **direkt nach einer Funktion, Klasse oder einem Modul** platzierst, wird er als **Dokumentation** erkannt:

```python
def hallo():
    """Gibt eine Begrüßung aus."""
    print("Hallo Welt")
```

Du kannst diesen später über `help(hallo)` abrufen.

---

## 🔍 Zusammenfassung

| Art             | Syntax                          | Zweck                     |
|------------------|----------------------------------|----------------------------|
| Einzeilig        | `# Kommentartext`               | Notizen, Erklärungen      |
| Mehrzeilig       | `''' Kommentar '''` oder `"""`  | Blockkommentare (inoffiziell) |
| Docstring        | Direkt nach `def`, `class`, `module` | Dokumentation abrufbar mit `help()` |

---

## ✅ Best Practices

- Nutze **Einzeiler** für kurze Hinweise.
- Verwende **Docstrings** für alle Funktionen, Klassen und Module.
- Halte Kommentare **kurz, klar und aktuell**.