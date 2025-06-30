# 🧾 Python – Variablen definieren und verwenden

Variablen sind **Namen**, die auf einen bestimmten **Wert im Speicher** zeigen. Sie dienen dazu, Informationen zu speichern und im Code weiterzuverwenden.

---

## 🧩 Definition von Variablen

In Python erfolgt die Zuweisung einer Variablen mit dem **Gleichheitszeichen `=`**:

```python
name = "Florian"
alter = 30
ist_aktiv = True
```

- Der **Name** steht links vom `=`
- Der **Wert** steht rechts vom `=`
- Der Typ wird **automatisch erkannt** (dynamisch typisiert)

---

## 🧩 Variablen verwenden (aufrufen)

Einmal definierte Variablen können später im Code **einfach durch ihren Namen** referenziert werden:

```python
vorname = "Anna"
print(vorname)
```

➡️ Gibt aus: `Anna`

---

## 🔁 Variablen neu zuweisen

Variablen lassen sich jederzeit mit einem neuen Wert überschreiben:

```python
x = 10
x = 20  # nun hat x den Wert 20
```

---

## ➕ Mehrere Zuweisungen gleichzeitig

```python
a, b = 1, 2
x = y = z = 0  # Alle drei erhalten den Wert 0
```

---

## ❌ Nicht erlaubte Namen

- Variablennamen **dürfen nicht** mit einer Zahl beginnen: `1name ❌`
- Keine Sonderzeichen außer `_` erlaubt
- Reservierte Wörter wie `if`, `class`, `def` dürfen **nicht** verwendet werden

---

## ✅ Gültige Namenskonventionen

| Stil            | Beispiel           | Beschreibung                 |
|------------------|--------------------|------------------------------|
| snake_case       | `benutzer_name`    | Python-Standard für Variablen |
| kein Bindestrich | `benutzer-name ❌` | Nicht erlaubt                |
| aussagekräftig   | `email_adresse`    | Vermeide `x`, `y`, `test`    |

---

## 🧠 Tipps

- Python ist **case-sensitive**: `Name ≠ name`
- Variablennamen sollten **bedeutungsvoll und lesbar** sein

---

## 📚 Beispiel

```python
titel = "Python-Grundlagen"
kapitel = 3
print("Lektion:", titel, "-", "Kapitel", kapitel)
```

➡️ Gibt aus: `Lektion: Python-Grundlagen - Kapitel 3`