# 📘 Dictionaries (`dict`)

Ein **Dictionary** in Python ist eine **strukturierte Sammlung von Schlüssel-Wert-Paaren**.  
Es ist vergleichbar mit einem **Wörterbuch** – ein Begriff (`Key`) hat eine Bedeutung (`Value`).

---

## 🔹 Was ist ein Dictionary?

Ein Dictionary speichert **beliebige Daten** – jeder `key` ist **eindeutig** und zeigt auf einen `value`.

```python
person = {
  "name": "Max",
  "alter": 30,
  "beruf": "Entwickler"
}
```

- `"name"` ist der **Schlüssel**
- `"Max"` ist der **Wert**

---

## 📦 Merkmale von Dictionaries

| Eigenschaft           | Erklärung                                              |
|------------------------|--------------------------------------------------------|
| Schlüssel (`key`)      | Müssen **eindeutig** sein, meist Strings              |
| Werte (`value`)        | Können beliebige Datentypen sein (auch Listen, Dicts) |
| Ungeordnet (bis 3.6)   | Ab Python 3.7 behalten sie die **Einfügereihenfolge** |
| Verändertbar (mutable) | Kann nachträglich bearbeitet werden                   |

---

## 🧱 Dictionary erstellen

### 🔸 Mit geschweiften Klammern

```python
auto = {
  "marke": "BMW",
  "baujahr": 2020,
  "farbe": "blau"
}
```

### 🔸 Mit `dict()`-Funktion

```python
auto = dict(marke="BMW", baujahr=2020, farbe="blau")
```

---

## 🔍 Typisches Einsatzszenario

Dictionaries sind ideal, wenn du **eindeutige Zuordnungen** brauchst:

```python
benutzer = {
  "username": "florian",
  "email": "f.fenzl@somebot.de",
  "aktiv": True
}
```

---

## ✅ Typische Werte im Dictionary

```python
profil = {
  "id": 123,
  "name": "Julia",
  "skills": ["Python", "Data Science"],
  "erfahrung": {
    "Jahre": 5,
    "Bereich": "KI"
  }
}
```

- Werte können **Listen, Zahlen, Strings, Booleans, sogar andere Dicts** sein.

---

## 📌 Syntax-Check

```python
# ✔️ gültig
info = {"x": 1, "y": 2}

# ❌ ungültig (Doppelte Keys)
fehler = {"a": 1, "a": 2}  # → letzter Wert überschreibt vorherigen
```

---

## ⚡ Wann Dictionaries verwenden?

| Anwendung                   | Dictionary ist sinnvoll |
|-----------------------------|--------------------------|
| Name + Adresse              | ✅ Ja                    |
| ID + Nutzerdaten            | ✅ Ja                    |
| Nur Wertelisten             | ❌ Nein (→ Liste besser) |
| Indexzugriff mit Zahlen     | ❌ Nein (→ Liste besser) |

---

## 📘 Fazit

Ein `dict` ist **schnell**, **flexibel** und **perfekt** geeignet, wenn man Werte mit **eindeutigen Schlüsseln** speichern will.

