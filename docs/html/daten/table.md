# `<table>` – Tabelle zur Datenpräsentation

## 🧩 Funktion

Das `<table>`-Element wird verwendet, um **strukturierte Daten in tabellarischer Form** darzustellen. Tabellen sind besonders geeignet für:

- Zahlenbasierte Inhalte
- Vergleichswerte
- Zeitpläne
- Kontaktlisten
- Produktdetails

> 📌 Tabellen sind **semantisch wertvoll**, wenn sie zur Darstellung von **Daten** (nicht Layout!) genutzt werden.

---

## ✅ Grundstruktur & Verwendung

```html
<table>
  <thead>
    <tr><th>Name</th><th>Alter</th></tr>
  </thead>
  <tbody>
    <tr><td>Anna</td><td>30</td></tr>
    <tr><td>Ben</td><td>28</td></tr>
  </tbody>
  <tfoot>
    <tr><td colspan="2">Ende der Liste</td></tr>
  </tfoot>
</table>
```

---

## 🔧 Struktur-Tags im Detail

| Tag        | Bedeutung                                           |
|------------|-----------------------------------------------------|
| `<table>`  | Das Tabellen-Element als Container                  |
| `<thead>`  | Kopfbereich der Tabelle                              |
| `<tbody>`  | Hauptinhaltsbereich der Tabelle                      |
| `<tfoot>`  | Fußzeile der Tabelle                                 |
| `<tr>`     | Tabellenreihe (table row)                            |
| `<th>`     | Kopfzelle mit **fetter Schrift** und semantischer Bedeutung |
| `<td>`     | Standardzelle (table data)                           |

---

## 🔧 Weitere Attribute

### Für `<table>`

| Attribut     | Beschreibung                         |
|--------------|--------------------------------------|
| `border`     | Einfache Rahmenlinie (veraltet)      |
| `class`      | CSS-Zuweisung                        |
| `style`      | Direktes Styling (z. B. Breite, Rand)|
| `summary`    | (veraltet) Kurzbeschreibung der Tabelle |
| `width`      | Breite der Tabelle (nicht empfohlen inline) |

### Für `<th>` und `<td>`

| Attribut   | Beschreibung                                |
|------------|---------------------------------------------|
| `colspan`  | Zelle über mehrere Spalten strecken         |
| `rowspan`  | Zelle über mehrere Zeilen strecken          |
| `headers`  | Verknüpfung zu einem `<th>`-Element         |
| `scope`    | `row`, `col` – Bereich des Spalten-/Zeilenkopfs |

---

## 🎨 Beispiel mit CSS

```html
<table class="kundenliste">
  <thead>
    <tr><th scope="col">Kunde</th><th scope="col">Land</th></tr>
  </thead>
  <tbody>
    <tr><td>Max</td><td>Deutschland</td></tr>
    <tr><td>Sofia</td><td>Schweiz</td></tr>
  </tbody>
</table>
```

```css
.kundenliste {
  width: 100%;
  border-collapse: collapse;
}

.kundenliste th,
.kundenliste td {
  border: 1px solid #ddd;
  padding: 0.8rem;
  text-align: left;
}

.kundenliste thead {
  background-color: #f5f5f5;
}
```

---

## ♿ Barrierefreiheit & Semantik

- Tabellen sollten **semantisch korrekt** aufgebaut sein
- `<th scope="col">` oder `<th scope="row">` hilft Screenreadern
- Komplexere Tabellen können `headers` und `id` verwenden
- Vermeide Tabellen ausschließlich für Layout-Zwecke

---

## ❌ Häufige Fehler

| Fehler                                  | Besser                                          |
|-----------------------------------------|-------------------------------------------------|
| Tabellen für visuelles Layout missbrauchen | Layout lieber mit CSS lösen                   |
| Nur `<td>` ohne `<thead>` / `<th>`      | Kopfbereiche klar definieren                   |
| Inhalte in Tabellen nicht semantisch verknüpft | Nutze `scope`, `headers`, `caption`          |

---

## 🧠 Erweiterungen

### Tabellenüberschrift mit `<caption>`

```html
<table>
  <caption>Kundendaten 2025</caption>
  ...
</table>
```

- Wird von Screenreadern zuerst vorgelesen
- Gibt Kontext zum Tabellendatensatz

---

## 🔄 Vergleich zu Listen

| Element    | Verwendung                         |
|------------|-------------------------------------|
| `<table>`  | Gitterartige Darstellung von Daten |
| `<ul>`, `<ol>` | Aufzählungen, Listenstruktur      |
| `<dl>`     | Begriffsdefinitionen, Beschreibungen|

---

## 📚 Fazit

Tabellen sind das **ideale Mittel für strukturierte Daten**.  
Mit klarer Struktur, sauberem HTML und passenden CSS-Styles lassen sich Inhalte übersichtlich und barrierefrei präsentieren.

> 💬 Als Nächstes: Möchtest du mit `<dl>` (Definitionslisten), Tabellenfilterung per JavaScript oder responsiven Tabellen weitermachen?