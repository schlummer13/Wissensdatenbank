# 🔐 Escape-Sequenzen in Strings

Escape-Sequenzen sind **besondere Zeichenkombinationen** in Strings, die **nicht wörtlich ausgegeben**, sondern **interpretiert** werden – z. B. als **neue Zeile**, **Tabulator** oder **Anführungszeichen**.

Sie beginnen **immer mit einem Backslash `\`**.

---

## 🧩 Warum braucht man Escape-Sequenzen?

- Um **Sonderzeichen** darzustellen
- Um Zeichen wie `"`, `'` oder `\` **in einem String zu nutzen**
- Um **Steuerzeichen** wie `\n` oder `\t` einzufügen

---

## 📜 Häufige Escape-Sequenzen

| Escape | Wirkung                     | Beispiel                        |
|--------|-----------------------------|----------------------------------|
| `\\`   | Backslash `\`               | `"C:\\Users\\Florian"`          |
| `\'`   | Einfaches Anführungszeichen | `'It\'s OK'`                    |
| `\"`   | Doppeltes Anführungszeichen | `"Er sagte: \"Hallo\""`         |
| `\n`   | Neue Zeile (Linebreak)      | `"Zeile 1\nZeile 2"`            |
| `\t`   | Tabulator (Einzug)          | `"Name:\tFlorian"`              |
| `\r`   | Carriage Return (selten)    | `"Text\rErsetzt"`               |
| `\b`   | Backspace (löscht davor)    | `"Helloo\b!"` → `"Hello!"`     |
| `\f`   | Seitenvorschub              | (kaum genutzt)                  |
| `\a`   | "Beep"-Ton (falls unterstützt) | (historisch)                |
| `\v`   | Vertikaler Tabulator        | (kaum genutzt)                  |
| `\ooo` | Oktalwert                   | `"\101"` → `"A"`                |
| `\xhh` | Hexadezimalwert             | `"\x41"` → `"A"`                |

---

## ✍️ Beispiel: Escape von Zeichen

```python
text = 'Er sagte: \'Hallo Welt!\''
print(text)
# Ausgabe: Er sagte: 'Hallo Welt!'
```

---

## ✍️ Beispiel: Pfade

```python
pfad = "C:\\Users\\Florian\\Desktop"
print(pfad)
# Ausgabe: C:\Users\Florian\Desktop
```

---

## ✅ Mehrzeilige Strings mit `\n`

```python
mehrzeilig = "Zeile 1\nZeile 2\nZeile 3"
print(mehrzeilig)
```

Ergebnis:

```
Zeile 1
Zeile 2
Zeile 3
```

---

## ⛔ Problem: Windows-Pfade

```python
pfad = "C:\newfolder\test.txt"
# → \n und \t werden als Steuerzeichen interpretiert
```

➡️ Verwende lieber:

- **Doppelte Backslashes:** `"C:\\newfolder\\test.txt"`
- Oder: **Raw-Strings** (siehe unten)

---

## 🧱 Raw-Strings (`r""`)

Ein **Raw-String** (`r"..."`) sagt Python, dass **keine Escape-Sequenzen** verarbeitet werden sollen.

```python
raw = r"C:\newfolder\test.txt"
print(raw)  # C:\newfolder\test.txt
```

Nützlich für **Reguläre Ausdrücke**, **Dateipfade**, u. v. m.

---

## 🔍 Unicode-Zeichen (Bonus)

```python
print("\u00A9")     # ©
print("\U0001F600") # 😀 (Emoji)
```

| Escape  | Beschreibung               |
|---------|----------------------------|
| `\uXXXX` | Unicode 4-stellig         |
| `\UXXXXXXXX` | Unicode 8-stellig     |

---

## 🧠 Zusammenfassung

| Funktion                 | Syntax-Beispiel         |
|--------------------------|--------------------------|
| Anführungszeichen im String | `"Er sagte: \"Hi\""` |
| Neue Zeile               | `"Zeile1\nZeile2"`       |
| Tabulator                | `"Name:\tWert"`          |
| Backslash                | `"C:\\Pfad"`             |
| Raw-String               | `r"C:\Pfad"`             |

---

> 🧩 **Tipp:** Immer wenn du ein Zeichen brauchst, das in der Tastaturfunktion steckt (z. B. Enter, Tab, Backslash), brauchst du wahrscheinlich eine Escape-Sequenz!