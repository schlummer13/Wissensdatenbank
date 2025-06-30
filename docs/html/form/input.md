# `<input>` – Formulareingabe

## 🧩 Funktion

Das `<input>`-Element ist eines der wichtigsten HTML-Formularelemente. Es dient zur **Erfassung von Benutzereingaben** aller Art – von einfachem Text bis hin zu Datumsauswahl, Datei-Upload oder Kontrollkästchen.  
Es ist ein **leeres Tag** (self-closing), d. h. es hat kein schließendes Tag wie `<input></input>`.

---

## ✅ Grundlegende Verwendung

```html
<input type="text" name="vorname" placeholder="Vorname" required />
```

Dieser Code erzeugt ein einzeiliges Texteingabefeld mit Platzhalter und Pflichtangabe.

---

## 🔧 Wichtige Attribute

| Attribut      | Beschreibung |
|---------------|--------------|
| `type`        | Definiert den Eingabetyp (z. B. Text, Passwort, Datei, usw.) |
| `name`        | Der Schlüsselname zur Identifikation beim Absenden des Formulars |
| `value`       | Voreingestellter oder zurückgegebener Wert |
| `placeholder` | Platzhaltertext, der bei leerem Feld angezeigt wird |
| `required`    | Markiert das Feld als Pflichtfeld |
| `readonly`    | Feld kann angezeigt, aber nicht verändert werden |
| `disabled`    | Deaktiviert das Feld vollständig |
| `autocomplete`| Schlägt gespeicherte Werte vor (z. B. Name, E-Mail) |
| `maxlength`, `minlength` | Begrenzung der Zeichenanzahl |
| `pattern`     | Regulärer Ausdruck für Formatvalidierung |
| `step`        | Schrittweite bei numerischen Eingaben (z. B. „0.5“) |
| `min`, `max`  | Wertebereich bei Zahlen, Datum, Zeit |

---

## 🧪 Übersicht: `type`-Varianten

Hier sind die gebräuchlichsten `type`-Werte des `<input>`-Elements:

### 🔤 Textbasierte Eingaben
| Typ         | Beschreibung |
|-------------|--------------|
| `text`      | Einzeilige Texteingabe |
| `password`  | Eingabe wird durch Punkte versteckt |
| `email`     | Validiert E-Mail-Adresse |
| `url`       | Validiert Webadressen |
| `search`    | Speziell für Suchfelder |
| `tel`       | Telefonnummern, oft mit Nummernblock |

### 🔘 Auswahlfelder
| Typ           | Beschreibung |
|---------------|--------------|
| `checkbox`    | Kontrollkästchen (Mehrfachauswahl möglich) |
| `radio`       | Optionsfeld (nur eine Auswahl pro Gruppe) |

### 🔢 Zahlen und Bereiche
| Typ         | Beschreibung |
|-------------|--------------|
| `number`    | Nur Zahlen erlaubt |
| `range`     | Schieberegler für Wertebereiche |

### 📅 Datum/Zeit
| Typ           | Beschreibung |
|---------------|--------------|
| `date`        | Datumsauswahl |
| `time`        | Zeiteingabe |
| `datetime-local` | Datum & Zeit ohne Zeitzone |
| `month`       | Auswahl von Monat & Jahr |
| `week`        | Auswahl nach Kalenderwoche |

### 🗂️ Sonstiges
| Typ         | Beschreibung |
|-------------|--------------|
| `file`      | Datei-Upload-Feld |
| `hidden`    | Nicht sichtbare Datenübermittlung |
| `color`     | Farbauswahl über Picker |
| `submit`    | Absende-Button |
| `reset`     | Formular zurücksetzen |
| `button`    | Allgemeiner Button ohne Funktion (kann JS-getriggert sein) |

---

## 🧠 Beispiele

### 🔑 Passwortfeld

```html
<input type="password" name="passwort" required />
```

**Beispiel:**<br>
<input type="password" name="passwort" style="border: 1px solid black" required  />

### ✅ Checkbox mit Standardwert

```html
<input type="checkbox" name="agb" value="akzeptiert" checked /> AGB akzeptieren
```
**Beispiel:**<br>
<input type="checkbox" name="agb" value="akzeptiert" checked /> AGB akzeptieren

### 🎯 Radio-Buttons

```html
<input type="radio" name="geschlecht" value="m" /> Männlich
<input type="radio" name="geschlecht" value="w" /> Weiblich
```
**Beispiel:**<br>
<input type="radio" name="geschlecht" value="m" /> Männlich
<input type="radio" name="geschlecht" value="w" /> Weiblich


### 📂 Datei-Upload

```html
<input type="file" name="profilbild" accept="image/*" />
```
**Beispiel**:<br>
<input type="file" name="profilbild" accept="image/*" />

---

## 💡 Tipps für gute Formulare

- Kombiniere `<input>` mit `<label>` zur besseren Bedienbarkeit und Barrierefreiheit.
- Nutze das `for`-Attribut von `<label>` mit der `id` des zugehörigen `<input>`:
  
  ```html
  <label for="email">E-Mail:</label>
  <input type="email" id="email" name="email" />
  ```

**Beispiel:**<br>
<label for="email">E-Mail:</label>
<input type="email" id="email" name="email" style="border: 1px solid black"/>

- Gruppiere verwandte Eingabefelder mit `<fieldset>` und `<legend>`.
- Validiere Eingaben zusätzlich mit JavaScript – HTML-Validation reicht oft nicht aus.
- Nutze `autocomplete="off"` nur, wenn du es wirklich brauchst (z. B. bei sensiblen Daten).

---

## 🧾 Fazit

Das `<input>`-Element ist extrem vielseitig und kann für fast jede Art von Benutzereingabe angepasst werden. Durch Kombination mit passenden Attributen und Typen entsteht ein **intuitives, barrierefreies und benutzerfreundliches Formular**.