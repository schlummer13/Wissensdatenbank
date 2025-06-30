# 🔗 Strings verknüpfen (Concatenation)

**String-Konkatenation** bedeutet, mehrere Zeichenketten zu **einem einzigen String zusammenzufügen**. In Python gibt es dafür verschiedene Methoden – je nach Bedarf und Lesbarkeit.

---

## ✅ Methode 1: `+` – Klassische Verkettung

```python
vorname = "Max"
nachname = "Mustermann"
name = vorname + " " + nachname
print(name)  # Max Mustermann
```

- Nutzt das `+`-Zeichen, um Strings direkt zu verbinden
- Einfach und intuitiv
- Achtung: **funktioniert nur mit Strings!**

```python
alter = 30
# print("Ich bin " + alter) ❌ Fehler
print("Ich bin " + str(alter))  # ✅ Ich bin 30
```

---

## ✅ Methode 2: `+=` – An String anhängen

```python
text = "Hallo"
text += " Welt"
print(text)  # Hallo Welt
```

- Fügt neuen Text **an bestehenden String an**
- Praktisch für dynamischen Aufbau in Schleifen

---

## ✅ Methode 3: `f-Strings` (empfohlen ab Python 3.6)

```python
name = "Florian"
stadt = "Berlin"
info = f"{name} wohnt in {stadt}"
print(info)  # Florian wohnt in Berlin
```

- **Klar & lesbar**
- **Performanter** als viele Verkettungen mit `+`
- Unterstützt **Ausdrücke** direkt:

```python
alter = 32
print(f"In 5 Jahren ist Florian {alter + 5} Jahre alt.")
```

---

## ✅ Methode 4: `format()` – Alternative zu f-Strings

```python
s = "Hallo {}, du hast {} neue Nachrichten.".format("Anna", 5)
print(s)  # Hallo Anna, du hast 5 neue Nachrichten.
```

- Kompatibel mit älteren Python-Versionen (<3.6)
- Flexibel mit Platzhaltern `{}`

```python
template = "{0} + {0} = {1}"
print(template.format("Apfel", "ApfelApfel"))  # Apfel + Apfel = ApfelApfel
```

---

## ✅ Methode 5: `join()` – Mehrere Strings effizient verbinden

```python
teile = ["HTML", "CSS", "JavaScript"]
text = ", ".join(teile)
print(text)  # HTML, CSS, JavaScript
```

- Perfekt für Listen von Strings
- Besser skalierbar als `+` in Schleifen

⚠️ `join()` funktioniert **nur mit Strings**, sonst gibt’s einen Fehler.

```python
zahlen = [1, 2, 3]
# ", ".join(zahlen) ❌ Fehler
print(", ".join(map(str, zahlen)))  # ✅ 1, 2, 3
```

---

## 🧪 Beispiel: Dynamischer Satzbau

```python
teile = ["Python", "macht", "Spaß"]
satz = " ".join(teile)
print(satz)  # Python macht Spaß
```

---

## 🔁 Beispiel mit Schleife

```python
teile = ["Teil1", "Teil2", "Teil3"]
text = ""
for t in teile:
    text += t + ", "
print(text)  # Teil1, Teil2, Teil3, 
```

➡️ **Besser:** mit `join()`:

```python
print(", ".join(teile))  # Teil1, Teil2, Teil3
```

---

## 🚫 Falsch: Zahlen mit + verketten

```python
# Fehler:
# print("Summe: " + 3 + 4)

# Richtig:
print("Summe: " + str(3 + 4))  # Summe: 7
```

---

## ✅ Zusammenfassung

| Methode      | Beschreibung                                 | Wann nutzen?                     |
|--------------|----------------------------------------------|----------------------------------|
| `+`          | Einfaches Verbinden                          | 2–3 Strings                      |
| `+=`         | Anfügen in Schleifen                         | dynamisch erweitern             |
| `f""`        | Moderne, lesbare Lösung                      | für Klarheit + Performance      |
| `format()`   | Ältere, flexible Alternative zu `f""`        | kompatibel mit älteren Pythons  |
| `"".join()`  | Für Listen & viele Teile                     | schnell, effizient              |

---

> 🔎 Tipp: Nutze `join()` für Listen, `f""` für einfache Lesbarkeit und `+` nur bei wenigen, klaren Fällen.