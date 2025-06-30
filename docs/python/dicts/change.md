# 🔧 Dictionary-Werte ändern (`dict change`)

Ein `dict` ist **veränderbar (mutable)** – du kannst Werte leicht aktualisieren oder neue hinzufügen.

---

## ✏️ Wert eines vorhandenen Schlüssels ändern

```python
person = {
  "name": "Anna",
  "alter": 28
}

person["alter"] = 29
print(person)  # {'name': 'Anna', 'alter': 29}
```

- Du schreibst einfach `dict[key] = neuer_wert`

---

## ➕ Neuen Schlüssel-Wert hinzufügen

```python
person["stadt"] = "Berlin"
print(person)  # {'name': 'Anna', 'alter': 29, 'stadt': 'Berlin'}
```

- Wenn der Schlüssel **nicht existiert**, wird er **neu erstellt**

---

## 🔄 Mehrere Einträge gleichzeitig ändern mit `.update()`

```python
person.update({
  "alter": 30,
  "beruf": "Data Analyst"
})
print(person)
# {'name': 'Anna', 'alter': 30, 'stadt': 'Berlin', 'beruf': 'Data Analyst'}
```

- Praktisch für **mehrere Änderungen auf einmal**
- Überschreibt vorhandene Keys oder fügt neue hinzu

---

## 🧠 Typische Anwendungsfälle

```python
# Zähler erhöhen
person["alter"] += 1

# String erweitern
person["name"] += " Müller"
```

---

## ⚠️ Was passiert bei einem falschen Key?

```python
person["email"] += "@domain.com"  # ❌ KeyError wenn nicht vorhanden!
```

➡️ **Besser absichern:**

```python
if "email" in person:
  person["email"] += "@domain.com"
else:
  person["email"] = "anna@domain.com"
```

---

## ✅ Zusammenfassung

| Aktion               | Code-Beispiel                           | Ergebnis                           |
|----------------------|------------------------------------------|-------------------------------------|
| Wert ändern          | `dict["key"] = neuer_wert`              | Überschreibt bestehenden Wert      |
| Wert hinzufügen      | `dict["neu"] = wert`                    | Fügt neues Paar ein                |
| Mehrere auf einmal   | `dict.update({...})`                    | Ändert & ergänzt                   |
| Absichern mit Check  | `if "key" in dict:`                     | Vermeidet Fehler                   |

---

> 🔁 Dictionaries in Python sind sehr flexibel und lassen sich leicht erweitern, ändern oder kombinieren.