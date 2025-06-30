# 🔢 Sets (Mengen) Einführung

Ein **Set** ist eine **ungeordnete Sammlung** von **einzigartigen Werten**.  
Das bedeutet: **Doppelte Elemente werden automatisch entfernt.**

Sets sind ideal, wenn du **nur eindeutige Werte** brauchst – z. B. für Filter, Vergleiche oder mathematische Mengenoperationen.

---

## 🧪 Set erstellen

```python
früchte = {"Apfel", "Banane", "Apfel", "Orange"}
print(früchte)  # {'Apfel', 'Banane', 'Orange'}
```

> ⚠️ Nur **einmalige Werte** bleiben enthalten  
> ⚠️ Reihenfolge ist **nicht garantiert**

---

## 🧱 Leeres Set erzeugen

```python
leeres_set = set()
```

> ⚠️ `{}` erzeugt ein **leeres Dictionary**, **nicht** ein Set!

---

## 🧩 Eigenschaften von Sets

| Merkmal             | Beschreibung                                  |
|---------------------|-----------------------------------------------|
| **Ungeordnet**      | Keine garantierte Reihenfolge                 |
| **Einzigartig**     | Keine Duplikate erlaubt                       |
| **Veränderlich**    | Kann Elemente hinzufügen/entfernen           |
| **Nicht indizierbar** | Kein Zugriff per Index wie bei Listen       |

---

## 📋 Datentyp prüfen

```python
zahlen = {1, 2, 3}
print(type(zahlen))  # <class 'set'>
```

---

## 🔁 Set mit Schleife durchlaufen

```python
farben = {"rot", "grün", "blau"}

for farbe in farben:
    print(farbe)
```

> ✅ Reihenfolge kann sich ändern  
> ❌ Kein Zugriff über `farben[0]`

---

## 🧠 Warum Sets?

Sets sind besonders nützlich, wenn du:

- **Duplikate entfernen** möchtest
- **Schnittmengen**, **Vereinigungen** oder **Unterschiede** berechnen willst
- **Schnelle Tests auf Vorhandensein** brauchst (`in` ist sehr schnell)

---

## 🎯 Beispiel: Duplikate automatisch entfernen

```python
namen = ["Anna", "Ben", "Anna", "Clara"]
einzigartig = set(namen)

print(einzigartig)  # {'Anna', 'Ben', 'Clara'}
```

---

## 📌 Typische Anwendungsfälle

| Problemstellung                   | Lösung mit Set                        |
|-----------------------------------|----------------------------------------|
| Doppelte aus Liste entfernen      | `set(liste)`                          |
| Ist ein Wert vorhanden?           | `wert in mein_set`                    |
| Unterschiede oder Gemeinsamkeiten | Mengenoperationen mit Sets            |
| Viele Elemente schnell vergleichen| Sets sind schneller als Listen        |

---

## ✅ Zusammenfassung

| Merkmal            | Set (`set`)                            |
|--------------------|-----------------------------------------|
| Duplikate erlaubt? | ❌ Nein                                 |
| Reihenfolge fix?   | ❌ Nein                                 |
| Veränderbar?       | ✅ Ja                                   |
| Zugriff per Index? | ❌ Nein                                 |
| Einsatzgebiete     | Daten filtern, vergleichen, analysieren|

---

> 💡 Sets sind einfach – aber extrem **mächtig**, wenn du **eindeutige Werte** brauchst.
>  
> In den nächsten Lektionen zeigen wir dir, **wie man Sets verändert und vergleicht.**