# 🧭 Zugriff auf Dictionary-Werte (`dict access`)

Ein Dictionary (`dict`) besteht aus **Key-Value-Paaren**. Um auf die Werte zuzugreifen, nutzt man den jeweiligen Schlüssel (Key).

---

## 🔑 Zugriff über eckige Klammern `[]`

```python
person = {
  "name": "Anna",
  "alter": 28,
  "stadt": "Berlin"
}

print(person["name"])   # Anna
print(person["alter"])  # 28
```

- Du gibst den **Schlüssel** an → bekommst den **Wert**
- ❗ Wenn der Key nicht existiert → `KeyError`

---

## 🛡️ Sicherer Zugriff mit `.get()`

```python
print(person.get("stadt"))         # Berlin
print(person.get("beruf", "n/a"))  # n/a
```

- `.get()` gibt `None` zurück, wenn der Schlüssel fehlt – **keine Fehlermeldung**
- Optional: **Standardwert** angeben, wenn Key fehlt

---

## 🔁 Zugriff in Schleifen

### 🔹 Alle Schlüssel durchlaufen

```python
for key in person:
  print(key, "→", person[key])
```

### 🔹 Nur Werte durchlaufen

```python
for value in person.values():
  print(value)
```

### 🔹 Schlüssel und Werte gleichzeitig

```python
for key, value in person.items():
  print(f"{key}: {value}")
```

---

## 📚 Zugriff auf verschachtelte Dictionaries

```python
benutzer = {
  "profil": {
    "vorname": "Lena",
    "nachname": "Meyer"
  }
}

print(benutzer["profil"]["vorname"])  # Lena
```

➡️ Mehrstufige Klammern für verschachtelte Daten

---

## ❓ Existiert der Schlüssel?

```python
if "alter" in person:
  print("Alter ist vorhanden")
```

- Vermeidet Fehler bei fehlenden Schlüsseln

---

## 🧠 Zusammenfassung

| Zugriffstyp       | Beispiel                         | Bemerkung                         |
|--------------------|----------------------------------|------------------------------------|
| Direkt             | `dict["key"]`                   | Gibt Fehler bei fehlendem Key     |
| Sicher             | `dict.get("key", default)`      | Kein Fehler bei fehlendem Key     |
| Durchlaufen        | `for key in dict:`              | Iteration über alle Keys          |
| Nur Werte          | `for v in dict.values()`        | Nur die Werte                     |
| Schlüssel + Wert   | `for k, v in dict.items()`      | Zugriff auf beide gleichzeitig    |
| Verschachtelt      | `dict["key1"]["key2"]`          | Zugriff auf geschachtelte Dicts   |
| Vorhanden?         | `"key" in dict`                 | Liefert `True`/`False`            |

---

> ✅ Der Zugriff auf Dictionary-Werte ist einfach, aber durch `.get()` und `.items()` auch sehr flexibel und sicher.