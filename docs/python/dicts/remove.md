# 🗑️ Dictionary-Werte entfernen (`dict remove`)

Ein Dictionary (`dict`) kann flexibel **Einträge löschen** – also Schlüssel mit ihren Werten entfernen. Dafür gibt es mehrere sichere und effiziente Methoden.

---

## ❌ Mit `del` löschen

```python
person = {"name": "Anna", "alter": 28}

del person["alter"]
print(person)  # {'name': 'Anna'}
```

- Entfernt **ein bestimmtes Schlüssel-Wert-Paar**
- ❗ Gibt einen **Fehler**, wenn der Key nicht existiert

➡️ Absichern:

```python
if "alter" in person:
  del person["alter"]
```

---

## 🧽 Mit `.pop()` löschen und Wert erhalten

```python
person = {"name": "Anna", "stadt": "Berlin"}

wert = person.pop("stadt")
print(wert)      # Berlin
print(person)    # {'name': 'Anna'}
```

- Löscht **und gibt den entfernten Wert zurück**
- Du kannst auch einen **Standardwert** angeben:

```python
person.pop("beruf", "nicht vorhanden")  # kein Fehler
```

---

## 🔁 Das letzte Element entfernen mit `.popitem()`

```python
daten = {"a": 1, "b": 2, "c": 3}
letzter = daten.popitem()

print(letzter)  # ('c', 3)
print(daten)    # {'a': 1, 'b': 2}
```

- Entfernt **das zuletzt hinzugefügte Paar** (Python 3.7+)
- Gibt ein `(key, value)`-Tupel zurück

---

## 🧹 Komplett leeren mit `.clear()`

```python
person.clear()
print(person)  # {}
```

- Entfernt **alle Einträge**
- Das Dictionary bleibt aber erhalten

---

## ✅ Zusammenfassung

| Methode          | Funktion                                 | Fehler bei fehlendem Key? |
|------------------|------------------------------------------|----------------------------|
| `del dict["x"]`  | Entfernt Key direkt                      | ✅ ja                      |
| `pop("x")`       | Entfernt Key & gibt Wert zurück          | ✅ ja, aber absicherbar    |
| `pop("x", def)`  | Sicher löschen mit Fallback              | ❌ nein                    |
| `popitem()`      | Letztes Element entfernen                | ✅ ja                      |
| `clear()`        | Alles entfernen                          | ❌ nein                    |

---

> 🧠 Nutze `pop()` für sicheres Löschen, `clear()` zum Zurücksetzen und `del` für gezieltes Entfernen – mit Vorsicht!