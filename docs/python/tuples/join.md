# 🔗 Tuple zusammenführen (Join/Concat)

Tuples sind **unveränderlich**, aber du kannst sie **durch Verkettung (Concatenation)** kombinieren. So entsteht ein **neues Tuple**, das alle Elemente enthält.

---

## ➕ Zwei Tuples zusammenführen

```python
a = (1, 2, 3)
b = (4, 5)

c = a + b
print(c)  # (1, 2, 3, 4, 5)
```

> ✅ Das Original bleibt unverändert – `+` erstellt ein **neues Tuple**.

---

## ➕ Mit leerem Tuple

```python
zahlen = (1, 2, 3)
leeres = ()

neu = zahlen + leeres
print(neu)  # (1, 2, 3)
```

---

## 🔁 Ein Tuple mehrfach wiederholen

```python
wort = ("Hey",)

echo = wort * 3
print(echo)  # ('Hey', 'Hey', 'Hey')
```

> 🔹 Das `*`-Symbol multipliziert das Tuple → n-fache Wiederholung.

> ⚠️ Beachte das Komma bei ein-elementigen Tuples: `("Hey",)` ist korrekt – ohne Komma wäre es nur ein String in Klammern!

---

## 🔀 Mit Variablen kombinieren

```python
vorname = ("Max",)
nachname = ("Mustermann",)

vollname = vorname + nachname
print(vollname)  # ('Max', 'Mustermann')
```

---

## 🧠 Auch mit Schleife zusammenfügen (dynamisch)

```python
teile = [(1, 2), (3,), (4, 5)]

ergebnis = ()
for t in teile:
    ergebnis += t

print(ergebnis)  # (1, 2, 3, 4, 5)
```

> ✅ Praktisch, wenn du mehrere Tuples aus einer Liste dynamisch verketten möchtest.

---

## 📌 Zusammenfassung

| Aktion                    | Syntax                             |
|---------------------------|-------------------------------------|
| Zwei Tuples verbinden     | `a + b`                            |
| Wiederholen eines Tuples  | `a * n`                            |
| Leeres Tuple anhängen     | `a + ()`                           |
| Dynamisch kombinieren     | Mit Schleife: `result += t`        |

---

## 🔥 Bonus: Strings joinen – Nicht mit Tuples verwechseln

Du kannst Tuples **nicht direkt mit `join()`** verketten – das funktioniert nur bei **Strings**.

```python
teile = ("Max", "Mustermann")

# Nur möglich, wenn alles Strings sind
print(" ".join(teile))  # Max Mustermann
```

---

> ✅ Verwende `+` und `*`, um Tuples zu verbinden oder zu wiederholen.
>  
> ❌ Methoden wie `.append()` oder `.extend()` funktionieren **nicht** – Tuples sind **unveränderbar**.