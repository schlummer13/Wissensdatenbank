# `<fieldset>` – Gruppierung von Formularfeldern

## 🧩 Funktion

Das `<fieldset>`-Element wird verwendet, um **verwandte Formularelemente logisch zu gruppieren**. Dadurch erhöht sich die **Übersichtlichkeit** und **Barrierefreiheit** eines Formulars.  
Gemeinsam mit `<legend>` dient es auch als **visuelle und semantische Strukturierung** – Screenreader und Browser erkennen so zusammengehörige Bereiche.

---

## ✅ Grundstruktur

```html
<fieldset>
  <legend>Persönliche Daten</legend>

  <label for="vorname">Vorname:</label>
  <input type="text" id="vorname" name="vorname" />

  <label for="nachname">Nachname:</label>
  <input type="text" id="nachname" name="nachname" />
</fieldset>
```

**Was passiert?**  
👉 Die Eingabefelder sind in einem **visuell abgegrenzten Bereich** mit Titel zusammengefasst.

---

## 🔧 Attribute von `<fieldset>`

| Attribut   | Beschreibung |
|------------|--------------|
| `disabled` | Deaktiviert alle enthaltenen Formularfelder |
| `form`     | Verbindet das Fieldset mit einem bestimmten Formular (nur wenn außerhalb `<form>`) |

### 🔧 `<legend>`-Element

| Verwendung | Beschreibung |
|------------|--------------|
| `<legend>` | Überschrift für das zugehörige Fieldset. Muss als erstes Element im Fieldset erscheinen. |

---

## 🧪 Beispiele

### 1. ✅ Formular mit zwei Gruppen

```html
<form>
  <fieldset>
    <legend>Login-Daten</legend>
    <label for="email">E-Mail:</label>
    <input type="email" id="email" name="email" required />

    <label for="passwort">Passwort:</label>
    <input type="password" id="passwort" name="passwort" required />
  </fieldset>

  <fieldset>
    <legend>Newsletter</legend>
    <label>
      <input type="checkbox" name="newsletter" /> Newsletter abonnieren
    </label>
  </fieldset>

  <button type="submit">Registrieren</button>
</form>
```

👉 Zwei logisch getrennte Gruppen, mit klarer Überschrift pro Abschnitt.

---

### 2. 🚫 Deaktiviertes Fieldset

```html
<fieldset disabled>
  <legend>Aktionscode</legend>
  <label for="code">Code:</label>
  <input type="text" id="code" name="code" />
</fieldset>
```

👉 Alle enthaltenen Felder sind **nicht editierbar** – praktisch z. B. bei abgelaufenen Aktionen oder schreibgeschützten Abschnitten.

---

### 3. 🎯 Fieldset außerhalb des Formulars (mit `form`)

```html
<form id="kontaktformular" action="/kontakt" method="post">
  <input type="text" name="betreff" placeholder="Betreff" />
</form>

<fieldset form="kontaktformular">
  <legend>Nachricht</legend>
  <textarea name="nachricht"></textarea>
</fieldset>
```

👉 Das Fieldset gehört visuell/logisch zum Formular, auch wenn es **außerhalb** im DOM steht.

---

## 🎨 Styling-Tipp mit CSS

```css
fieldset {
  border: 2px solid #ccc;
  padding: 1em;
  margin-bottom: 1em;
  border-radius: 8px;
}

legend {
  font-weight: bold;
  padding: 0 10px;
}
```

👉 So sieht das Fieldset modern und abgerundet aus. Standard-Styling ist oft sehr rudimentär.

---

## ♿ Barrierefreiheit & UX

- **Screenreader erkennen Fieldsets als Gruppierung**, was insbesondere bei komplexen Formularen wichtig ist (z. B. medizinische Angaben, Adressen etc.).
- Verwende `<legend>` als **klare Beschreibung**, nicht als visuellen Titel missbrauchen.
- Pro Fieldset **eine zentrale Aufgabe**: z. B. Kontaktdaten, Zahlungsoptionen, Lieferadresse etc.

---

## 🧾 Best Practices

- Verwende Fieldsets, um **lange Formulare logisch zu unterteilen**.
- Nutze ein `<legend>` **als erste Kindelement**, um Barrierefreiheit zu gewährleisten.
- Verwende Fieldsets **nicht für Layout-Zwecke** – dafür besser `<div>` & CSS.
- Aktiviere oder deaktiviere Formulareingaben global mit `<fieldset disabled>`, statt jeden Input einzeln.

---

## 📚 Fazit

Das `<fieldset>`-Element ist ein **semantisch wertvolles Tool**, um Formulare strukturiert, zugänglich und optisch ansprechend zu gestalten. Zusammen mit `<legend>` schafft es klare Gliederung – sowohl für Menschen als auch für Maschinen.

