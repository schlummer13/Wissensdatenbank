# 🔗 Sets zusammenfügen (Join)

In Python kannst du mehrere `set`-Objekte zu einem neuen Set **vereinigen**, um alle **einzigartigen** Elemente zu erhalten. Duplizierte Elemente werden dabei **automatisch entfernt**.

---

## 🔹 `union()` – Vereinigung zweier oder mehrerer Sets

```python
a = {1, 2, 3}
b = {3, 4, 5}

ergebnis = a.union(b)
print(ergebnis)  # {1, 2, 3, 4, 5}
```

- Gibt ein **neues Set** zurück
- Entfernt automatisch Duplikate

Auch mit mehreren Sets möglich:

```python
x = {1, 2}
y = {2, 3}
z = {3, 4}

gesamt = x.union(y, z)
print(gesamt)  # {1, 2, 3, 4}
```

---

## 🔸 `|` (Pipe-Operator) – Kurzform von `union()`

```python
a = {1, 2}
b = {2, 3}

print(a | b)  # {1, 2, 3}
```

---

## 🔄 `update()` – In-place Join (ändert Originalset)

```python
a = {1, 2}
b = {2, 3}

a.update(b)
print(a)  # {1, 2, 3}
```

- Ergänzt `a` direkt mit den Werten aus `b`
- **Verändert das ursprüngliche Set** (kein neues Objekt)

---

## 🧪 Beispiel: Mehrere Sets verbinden

```python
python = {"if", "else", "def"}
java = {"if", "switch", "class"}
js = {"function", "class", "if"}

alle = python.union(java, js)
print(alle)
# {'switch', 'else', 'function', 'if', 'def', 'class'}
```

---

## 📌 Wichtiges zu beachten

| Methode     | Beschreibung                            | Gibt neues Set zurück? |
|-------------|-----------------------------------------|-------------------------|
| `a.union(b)`| Vereinigt Inhalte, verändert nichts     | ✅ Ja                   |
| `a | b`     | Kurzform von `union()`                  | ✅ Ja                   |
| `a.update(b)` | Fügt `b`-Inhalte **in `a` ein**       | ❌ Nein (verändert `a`) |

---

## ✅ Zusammenfassung

| Ziel                      | Methode            |
|---------------------------|--------------------|
| Zwei Sets verbinden       | `a.union(b)`       |
| Mehrere Sets verbinden    | `a.union(b, c, d)` |
| Direkt in `a` speichern   | `a.update(b)`      |
| Kurz schreiben            | `a | b`            |

---

> 💡 Perfekt zum Kombinieren mehrerer Wertelisten ohne Duplikate – z. B. Benutzerrollen, Tags, Kategorien usw.