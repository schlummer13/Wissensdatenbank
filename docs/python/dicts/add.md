# ➕ Elemente zu Dictionaries hinzufügen

Ein **Dictionary (dict)** speichert Daten als Schlüssel-Wert-Paare. Neue Einträge lassen sich einfach hinzufügen – mit klarer und intuitiver Syntax.

---

## 📌 Grundregel: Neue Schlüssel direkt setzen

```python
person = {"name": "Anna"}

# Neuen Schlüssel hinzufügen
person["alter"] = 30

print(person)  # {'name': 'Anna', 'alter': 30}
```

- Gibt es den Schlüssel noch nicht, wird er **neu angelegt**
- Gibt es ihn bereits, wird der **Wert überschrieben**

---

## 🧠 Auch verschachtelt möglich

```python
person["adresse"] = {
  "stadt": "Berlin",
  "plz": "10115"
}
```

➡️ Jetzt enthält das Dictionary ein **verschachteltes Dictionary** als Wert.

---

## 🔄 Mehrere Werte gleichzeitig mit `update()`

```python
person.update({
  "beruf": "Entwicklerin",
  "verheiratet": False
})
```

- Fügt mehrere Schlüssel-Wert-Paare auf einmal hinzu
- Überschreibt bestehende Werte, wenn Schlüssel schon existieren

---

## 🔍 Bedingt mit `setdefault()`

```python
# Wenn "sprache" fehlt, hinzufügen mit Default-Wert
person.setdefault("sprache", "Deutsch")
```

- Gibt vorhandenen Wert zurück oder legt neuen an
- Praktisch für sichere Defaults

---

## 🧪 Beispiel: Kontaktdaten ergänzen

```python
kontakt = {
  "name": "Florian"
}

# Telefonnummer hinzufügen
kontakt["telefon"] = "123-456"

# E-Mail nur, wenn noch nicht vorhanden
kontakt.setdefault("email", "info@example.com")

# Beruf hinzufügen via update()
kontakt.update({"beruf": "Datenanalyst"})

print(kontakt)
```

➡️ Ergebnis:
```python
{
  "name": "Florian",
  "telefon": "123-456",
  "email": "info@example.com",
  "beruf": "Datenanalyst"
}
```

---

## ✅ Zusammenfassung

| Technik               | Beschreibung                                 |
|------------------------|----------------------------------------------|
| `dict[key] = wert`     | Standardmethode, neuen Key anlegen oder überschreiben |
| `update({...})`        | Mehrere Paare auf einmal hinzufügen          |
| `setdefault()`         | Nur hinzufügen, wenn Key noch nicht vorhanden |

---

> 💡 Tipp: Du kannst Dictionaries dynamisch erweitern – auch während einer Schleife oder über User-Input.