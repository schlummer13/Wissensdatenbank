# 🧱 Verschachtelte Dictionaries (`nested dicts`)

Ein **verschachteltes Dictionary** (engl. *nested dictionary*) ist ein Dictionary, das **andere Dictionaries als Werte** enthält. So lassen sich komplexe Datenstrukturen übersichtlich darstellen – z. B. Personen, Produkte oder Datenbanken.

---

## 📦 Beispiel – Einfaches verschachteltes Dictionary

```python
person = {
  "name": "Anna",
  "adresse": {
    "stadt": "Berlin",
    "plz": "10115"
  }
}
```

---

## 🔍 Auf verschachtelte Daten zugreifen

```python
print(person["adresse"]["stadt"])  # Berlin
```

➡️ Du greifst **Schritt für Schritt** auf die verschachtelten Ebenen zu:  
`dict[äußerer_key][innerer_key]`

---

## ✏️ Werte ändern

```python
person["adresse"]["plz"] = "10117"
```

➡️ Inneres Dictionary wird wie gewohnt modifiziert

---

## ➕ Neue Schlüssel hinzufügen

### Auf oberster Ebene:

```python
person["beruf"] = "Analystin"
```

### Innerhalb:

```python
person["adresse"]["straße"] = "Musterstraße 5"
```

---

## 🔁 Schleifen über verschachtelte Dictionaries

```python
for key, value in person.items():
    if isinstance(value, dict):
        for sub_key, sub_value in value.items():
            print(f"{key} → {sub_key}: {sub_value}")
    else:
        print(f"{key}: {value}")
```

➡️ Prüft, ob ein Wert selbst ein Dictionary ist und durchläuft es dann

---

## 🧱 Struktur mit mehreren Objekten

```python
personen = {
  "anna": {"alter": 28, "stadt": "Berlin"},
  "ben": {"alter": 35, "stadt": "Hamburg"}
}
```

### Zugriff:

```python
print(personen["ben"]["stadt"])  # Hamburg
```

---

## 🧪 Praktische Anwendung

```python
for name, daten in personen.items():
    print(f"{name.title()} ist {daten['alter']} Jahre alt und wohnt in {daten['stadt']}.")
```

➡️ Beispielausgabe:
```
Anna ist 28 Jahre alt und wohnt in Berlin.
Ben ist 35 Jahre alt und wohnt in Hamburg.
```

---

## ✅ Zusammenfassung

| Aktion                     | Beispiel                                       |
|----------------------------|------------------------------------------------|
| Zugriff auf verschachtelt  | `dict["key"]["subkey"]`                       |
| Wert ändern                | `dict["key"]["subkey"] = wert`                |
| Neues hinzufügen           | `dict["key"]["neuer"] = wert`                 |
| Überprüfen mit `isinstance`| `isinstance(value, dict)`                     |
| Mehrstufige Struktur       | Ideal für komplexe Informationen              |

---

> 🧠 Tipp: Für tiefe oder dynamische Strukturen kann auch ein `defaultdict` oder `get()` nützlich sein, um Fehler bei fehlenden Keys zu vermeiden.