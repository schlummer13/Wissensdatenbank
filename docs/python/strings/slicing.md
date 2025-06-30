# ✂️ String Slicing

**Slicing** bedeutet: Einen Teilstring (Ausschnitt) aus einem String entnehmen – ähnlich wie ein Messer, das einen Text in Stücke schneidet.

Python bietet dafür eine einfache, aber sehr **mächtige Syntax**.

---

## 📌 Grundlagen der Slicing-Syntax

```python
text[start:stop:step]
```

| Teil     | Bedeutung                              |
|----------|-----------------------------------------|
| `start`  | Index, bei dem das Slicing beginnt     |
| `stop`   | Index, **vor dem** das Slicing endet (ausschließend) |
| `step`   | Schrittweite (z. B. jedes 2. Zeichen)   |

> Wichtig: **Indexe starten bei 0**

---

## 🧪 Beispiele

```python
wort = "Python"
```

| Ausdruck           | Ergebnis | Erklärung                          |
|--------------------|----------|-------------------------------------|
| `wort[0]`          | `"P"`    | erstes Zeichen                     |
| `wort[1:4]`        | `"yth"`  | Zeichen 1 bis **3** (4 wird **nicht** mitgenommen) |
| `wort[:3]`         | `"Pyt"`  | von Anfang bis Index 3 (exklusiv)  |
| `wort[2:]`         | `"thon"` | von Index 2 bis zum Ende           |
| `wort[-1]`         | `"n"`    | letztes Zeichen                    |
| `wort[-3:-1]`      | `"ho"`   | drittletztes bis zweitletztes      |
| `wort[::2]`        | `"Pto"`  | jedes 2. Zeichen                   |
| `wort[::-1]`       | `"nohtyP"` | Umkehrung des Strings             |

---

## 🧠 Negative Indizes

Python erlaubt **negative Indizes**:

- `-1` = letztes Zeichen
- `-2` = vorletztes Zeichen
- usw.

Das ist **besonders nützlich** zum Rückwärtslesen:

```python
name = "Florian"
print(name[-3:])  # "ian"
```

---

## 🎯 Schrittweite (step)

```python
text = "abcdefghij"
print(text[::2])   # a c e g i
print(text[1::2])  # b d f h j
print(text[::-1])  # rückwärts
print(text[::-2])  # jedes 2. Zeichen rückwärts: j h f d b
```

---

## 🚫 Grenzen & Verhalten

- **`stop` ist exklusiv**: Das Zeichen an dieser Stelle wird nicht mehr genommen.
- Ist `start > stop` und `step` positiv → leere Zeichenkette!
- `step = 0` ergibt **Fehler**: `ValueError: slice step cannot be zero`

---

## 💡 Praktische Anwendungsbeispiele

### 1. Erste Zeichen extrahieren

```python
s = "Hallo Welt"
print(s[:5])  # "Hallo"
```

### 2. Domain aus E-Mail

```python
email = "user@example.com"
domain = email[email.index("@")+1:]
print(domain)  # "example.com"
```

### 3. String umdrehen

```python
s = "abcde"
print(s[::-1])  # "edcba"
```

### 4. Entfernen von Prefix

```python
s = "123-456-789"
print(s[4:])  # "456-789"
```

---

## 🧪 Slicing mit Variablen

```python
text = "Datenanalyse"
start = 2
stop = 8
print(text[start:stop])  # "tenana"
```

---

## 🧰 Slicing ist auch bei:

- **Listen**, **Tupel**, **Byte-Objekten**, **Ranges**, etc. anwendbar
- Beispiel mit Liste:

```python
zahlen = [0, 1, 2, 3, 4, 5]
print(zahlen[1:4])  # [1, 2, 3]
```

---

## ✅ Zusammenfassung

| Funktion                  | Ausdruck                | Ergebnis          |
|---------------------------|--------------------------|-------------------|
| Ersten Teil holen         | `s[:n]`                 | Anfang bis n-1    |
| Letzten Teil holen        | `s[-n:]`                | Letzte n Zeichen  |
| Mitte herausschneiden     | `s[2:5]`                | Index 2–4         |
| Rückwärts lesen           | `s[::-1]`               | Umgekehrt         |
| Jedes 2. Zeichen          | `s[::2]`                | z. B. a c e       |

---

## 📘 Tipp

Du kannst `slice(start, stop, step)` auch als Objekt verwenden:

```python
s = "Beispieltext"
teil = slice(1, 8, 2)
print(s[teil])  # "epit"
```

---

> Slicing ist eine **fundamentale Technik**, um in Python effizient mit Strings und anderen sequenziellen Datentypen zu arbeiten.