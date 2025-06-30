# 🌍 Python – `global` Statement

Mit dem `global`-Statement kannst du innerhalb einer Funktion auf eine **globale Variable** zugreifen und sie **verändern**.

---

## 🧩 Was ist eine globale Variable?

Variablen, die **außerhalb** von Funktionen definiert sind, nennt man **global**:

```python
zähler = 0  # globale Variable
```

Standardmäßig kann man innerhalb einer Funktion **lesen**, aber **nicht schreiben**, ohne `global` zu verwenden.

---

## ⚠️ Ohne `global` – Fehlverhalten

```python
x = 10

def setze_wert():
    x = 5  # erstellt eine neue lokale Variable x!

setze_wert()
print(x)  # → 10 (nicht verändert!)
```

- In diesem Beispiel wird `x` **lokal überschrieben**, nicht global verändert.

---

## ✅ Mit `global` – richtige Veränderung

```python
x = 10

def setze_wert():
    global x
    x = 5  # verändert die globale Variable

setze_wert()
print(x)  # → 5
```

---

## 🧠 Regeln

- `global` muss **innerhalb der Funktion** deklariert werden
- Es betrifft nur Variablen **mit genau diesem Namen**
- `global` sollte **sparsam** verwendet werden (kann Code schwerer verständlich machen)

---

## 📚 Beispiel: globaler Zähler

```python
zähler = 0

def inkrementieren():
    global zähler
    zähler += 1

inkrementieren()
inkrementieren()
print(zähler)  # → 2
```

---

## ✅ Zusammenfassung

| Verhalten            | Wirkung                                    |
|----------------------|--------------------------------------------|
| Ohne `global`        | erstellt eine **neue lokale** Variable     |
| Mit `global`         | greift auf **globale** Variable zu         |
| Empfehlung           | Nur verwenden, wenn es **wirklich nötig** ist |