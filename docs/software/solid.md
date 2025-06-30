# 🧱 SOLID – Die 5 Prinzipien guter objektorientierter Softwareentwicklung

**SOLID** ist ein Akronym für **fünf Grundprinzipien**, die helfen, **flexiblen, wartbaren und fehlerarmen Code** zu schreiben – besonders im objektorientierten Paradigma.

> Entwickelt wurde das Konzept unter anderem von **Robert C. Martin (Uncle Bob)**.

---

## 🧠 Warum SOLID?

| Vorteil                   | Bedeutung                                                  |
|---------------------------|-------------------------------------------------------------|
| 🛠 Weniger Bugs            | Bessere Struktur = weniger versteckte Fehlerquellen         |
| 🔁 Leicht erweiterbar      | Neue Features lassen sich einfacher integrieren             |
| 👨‍🔧 Bessere Wartbarkeit   | Klar getrennte Zuständigkeiten                             |
| 🔍 Testbarkeit             | Isolierte Einheiten lassen sich einfacher testen            |
| 🔄 Wiederverwendbarkeit   | Module können in anderen Projekten genutzt werden           |

---

## 🧩 Was bedeutet SOLID?

| Buchstabe | Prinzip                              | Deutsch                              |
|-----------|---------------------------------------|---------------------------------------|
| **S**     | Single Responsibility Principle       | **Einzelverantwortungsprinzip**       |
| **O**     | Open/Closed Principle                 | **Offen für Erweiterung, geschlossen für Änderung** |
| **L**     | Liskov Substitution Principle         | **Ersetzbarkeit durch Subklassen**    |
| **I**     | Interface Segregation Principle       | **Schnittstellenaufteilung**          |
| **D**     | Dependency Inversion Principle        | **Abhängigkeitsumkehr**               |

---

## 🔹 S – Single Responsibility Principle (SRP)

> **Eine Klasse sollte nur einen Grund zur Änderung haben.**

### ❌ Schlechter Stil:

```js
class User {
  saveToDatabase() { ... }
  renderProfileHTML() { ... }
}
```

➡️ Diese Klasse hat zwei Verantwortungen: Daten + UI

### ✅ Besser:

```js
class User {
  // nur Datenlogik
}

class UserRenderer {
  renderProfileHTML(user) { ... }
}
```

---

## 🔹 O – Open/Closed Principle (OCP)

> **Softwaremodule sollen offen für Erweiterung, aber geschlossen für Änderung sein.**

### ❌ Schlechter Stil:

```js
function berechnePreis(typ, betrag) {
  if (typ === "standard") return betrag;
  if (typ === "premium") return betrag * 0.9;
}
```

➡️ Jeder neue Typ ändert den Code.

### ✅ Besser:

```js
class Preisregel {
  berechne(betrag) { return betrag; }
}

class PremiumRegel extends Preisregel {
  berechne(betrag) { return betrag * 0.9; }
}
```

➡️ Neue Logik = neue Klasse, kein Code ändern

---

## 🔹 L – Liskov Substitution Principle (LSP)

> **Subklassen sollen sich wie ihre Elternklassen verhalten – ohne Fehler zu erzeugen.**

### ❌ Problematisch:

```js
class Rechteck {
  setBreite(b) { ... }
  setHöhe(h) { ... }
}

class Quadrat extends Rechteck {
  // Höhe und Breite müssen immer gleich bleiben ⇒ LSP verletzt
}
```

### ✅ Lösung:

- **Quadrat** sollte **nicht** von Rechteck erben
- Statt Vererbung: eigene Klasse oder Komposition

---

## 🔹 I – Interface Segregation Principle (ISP)

> **Lieber viele kleine, spezialisierte Schnittstellen statt einer großen.**

### ❌ Schlechter Stil:

```ts
interface Tier {
  laufen();
  fliegen();
}
class Hund implements Tier {
  laufen() {}
  fliegen() {} // Unsinn!
}
```

### ✅ Besser:

```ts
interface Läufer {
  laufen();
}
interface Flieger {
  fliegen();
}
class Hund implements Läufer { ... }
```

➡️ Nur das implementieren, was gebraucht wird

---

## 🔹 D – Dependency Inversion Principle (DIP)

> **High-Level-Module sollten nicht von Low-Level-Modulen abhängen. Beide sollten von Abstraktionen abhängen.**

### ❌ Schlechter Stil:

```js
class MySQL {
  speichereDaten(daten) { ... }
}

class NutzerService {
  constructor() {
    this.db = new MySQL();
  }
}
```

➡️ Direkt abhängig von konkreter Datenbank

### ✅ Besser:

```js
class NutzerService {
  constructor(datenbank) {
    this.db = datenbank;
  }
}
```

➡️ `MySQL`, `MongoDB`, `InMemory` – beliebig austauschbar  
➡️ Perfekt für Tests (z. B. Mocking möglich)

---

## ✅ Zusammenfassung

| Prinzip     | Merksatz                                   |
|-------------|---------------------------------------------|
| **S**       | Eine Klasse = eine Aufgabe                 |
| **O**       | Erweitern ohne Code zu ändern              |
| **L**       | Subklassen verhalten sich wie Eltern       |
| **I**       | Nur Schnittstellen nutzen, die man braucht |
| **D**       | Abhängigkeiten umdrehen – auf Abstraktion setzen |

---

## 📘 Ressourcen

- 📖 *Clean Code* – Robert C. Martin
- 📖 *Agile Softwareentwicklung: Prinzipien, Muster und Praktiken* – Martin & Martin
- [https://solidjs.com](https://solidjs.com) (nicht zu verwechseln mit dem JS-Framework gleichen Namens 😉)

---

## 💡 Fazit

> „Guter Code ist nicht der, der läuft – sondern der, der verstanden, geändert und wiederverwendet werden kann.“

- Die SOLID-Prinzipien helfen dir, **nachhaltig guten Code** zu schreiben
- Sie sind **nicht zwingend**, aber **empfohlen** – besonders bei größeren Projekten
- Auch in **nicht-objektorientierten** Sprachen wie JavaScript oder Python anwendbar