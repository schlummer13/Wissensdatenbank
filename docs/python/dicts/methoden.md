# 🧰 Dictionary Methoden

Python bietet viele nützliche Methoden, um mit Dictionaries effizient zu arbeiten. Diese Methoden helfen beim **Zugriff**, **Bearbeiten**, **Kopieren**, **Suchen** und **Organisieren** von Daten.

---

## 🔎 `get()` – Sicherer Zugriff auf Werte

```python
person = {"name": "Anna", "alter": 30}

print(person.get("name"))         # Anna
print(person.get("stadt", "N/A")) # N/A (Defaultwert, wenn Key fehlt)
```

- Gibt `None` zurück, wenn Schlüssel nicht existiert (oder einen selbst definierten Standardwert).
- Verhindert Fehler wie `KeyError`.

---

## 🔧 `update()` – Dictionary aktualisieren oder erweitern

```python
person.update({"beruf": "Analystin", "alter": 31})
```

- Fügt neue Schlüssel-Werte-Paare hinzu oder **überschreibt** bestehende.

---

## 🗑️ `pop()` – Schlüssel entfernen und Wert zurückgeben

```python
wert = person.pop("alter")
# Entfernt "alter" und gibt 31 zurück
```

- Wenn der Schlüssel fehlt, gibt es einen Fehler – es sei denn, du gibst einen Defaultwert an: `person.pop("xyz", "nicht da")`

---

## 🧹 `clear()` – Alle Inhalte löschen

```python
person.clear()
```

➡️ Dictionary ist danach leer: `{}`

---

## 📋 `copy()` – Flache Kopie erstellen

```python
neu = person.copy()
```

- Erstellt eine **flache Kopie** (kein `deep copy`!)
- Änderungen am Original betreffen die Kopie **nicht** – solange es keine verschachtelten Strukturen sind.

---

## 🔑 `keys()` – Alle Schlüssel als Ansicht

```python
for key in person.keys():
    print(key)
```

- Gibt `dict_keys` Objekt zurück (ähnlich wie Liste, aber keine echte Liste).
- Kann mit `list()` in Liste umgewandelt werden.

---

## 🔢 `values()` – Alle Werte

```python
for wert in person.values():
    print(wert)
```

---

## 🧩 `items()` – Alle Schlüssel-Wert-Paare

```python
for key, value in person.items():
    print(f"{key}: {value}")
```

➡️ Ideal für `for`-Schleifen!

---

## 🔍 `in` – Schlüssel prüfen

```python
if "name" in person:
    print("Name existiert")
```

---

## 🚧 `setdefault()` – Wert zurückgeben oder erstellen

```python
farbe = person.setdefault("farbe", "blau")
```

- Gibt vorhandenen Wert zurück – oder setzt und gibt Default zurück, wenn noch nicht vorhanden.

---

## 🧪 Beispielübersicht

```python
person = {"name": "Tom"}

person.get("name")        # "Tom"
person.get("alter", 0)    # 0 (nicht vorhanden)

person.update({"alter": 25})
person.pop("name")        # "Tom"
person.setdefault("stadt", "Berlin")

copy = person.copy()
person.clear()

list(person.keys())       # Alle Keys als Liste
```

---

## ✅ Zusammenfassung

| Methode         | Zweck                               |
|------------------|--------------------------------------|
| `get()`         | Sicherer Zugriff mit Fallback        |
| `update()`      | Daten ergänzen oder ändern           |
| `pop()`         | Element löschen mit Rückgabe         |
| `clear()`       | Alles löschen                        |
| `copy()`        | Kopie erzeugen                       |
| `keys()`        | Alle Schlüssel                       |
| `values()`      | Alle Werte                           |
| `items()`       | Alle Schlüssel-Wert-Paare            |
| `setdefault()`  | Sicher einfügen + Rückgabe           |
| `in`            | Existiert ein Schlüssel?             |

---

> 🧠 Tipp: Viele dieser Methoden geben keine Listen zurück, sondern **spezielle View-Objekte** (`dict_keys`, `dict_values`), die du mit `list()` umwandeln kannst – wenn du sie sortieren, zählen oder manipulieren willst.