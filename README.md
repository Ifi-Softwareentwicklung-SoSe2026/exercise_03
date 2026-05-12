<!--

author:   Volker Göhler
email:    volker.goehler@informatik.tu-freiberg.de
version:  0.0.3
language: de
narrator: Deutsch Female

edit: true
date: 2026-05-07

icon: img/TUBAF_Logo_blau.png
comment:  Übung Softwareentwicklung 03

import: https://raw.githubusercontent.com/liaScript/mermaid_template/master/README.md
import: https://raw.githubusercontent.com/liascript-templates/plantUML/master/README.md

link:   https://raw.githubusercontent.com/vgoehler/LiaScript_CSS_Provider/refs/heads/main/dist/university.css

tags: [ Sommersemester2026, Softwareentwicklung, Übung03]

-->

[![LiaScript Course](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://liascript.github.io/course/?https://raw.githubusercontent.com/Ifi-Softwareentwicklung-SoSe2026/exercise_03/refs/heads/main/README.md)

#  Aufgabe 03

Softwareentwicklung SoSe2026
============================

Bearbeitungszeitraum
====================

*17. Mai - 30. Mai 2026*

## Offene Fragen aus Aufgabe 02

Die folgenden Aufgaben aus der letzten Einheit (Aufgabe 02) sollten bearbeitet worden sein:

Aufgabe 1: Klassenhierarchie für Himmelskörper
--------------------

- [ ] Wurde eine abstrakte Basisklasse `Himmelskoerper` erstellt?
- [ ] Wurden die Klassen `Stern`, `Planet` und `Mond` von `Himmelskoerper` abgeleitet?
- [ ] Wurden Constructor-Chaining mit `base()` verwendet?
- [ ] Wurde `ToString()` in den abgeleiteten Klassen überschrieben?

Aufgabe 2: Bahndaten (Immutable DataBean)
--------------------

- [ ] Wurde eine immutable Klasse `Bahndaten` mit `init;`-Properties erstellt?
- [ ] Wurden `ToString()` und `GetHashCode()` implementiert?

Aufgabe 3: Speichervisualisierung
--------------------

- [ ] Wurde eine statische Klasse `SpeicherVisualisierer` mit `params object[]` erstellt?
- [ ] Wird für jedes Objekt Typ, Wert und HashCode ausgegeben?

Aufgabe 4: Bahnvisualisierung (ASCII)
--------------------

- [ ] Wurde eine Klasse `BahnVisualisierer` erstellt, die von `BahnBasic` erbt?
- [ ] Wird die Bahn eines Himmelskörpers als ASCII-Diagramm gezeichnet?
- [ ] Wird die Exzentrizität der Bahn berücksichtigt?

## Neue Aufgaben für diese Woche

Wir erweitern die Raumfahrt-Mission um Konzepte der **Schnittstellenprogrammierung**, **generische Kollektionen** und den **Umgang mit Dateien**. Zudem üben wir die **kollaborative Arbeit mit Git und GitHub**.

### **📌 Vorbereitung: Projekt aktualisieren**

1. Nutze das bestehende **C#-Konsolenprojekt** `RaumfahrtMission` aus Aufgabe 02.
2. Füge die finalen Klassen aus Aufgabe 02 hinzu (falls noch nicht vorhanden), die Version aus `solutions` im `exercise_02` Repo kann als Ausgangspunkt genutzt werden.
3. Alle Klassen sollen weiterhin im Namespace **`RaumfahrtMission`** liegen.

### **🛠️ Aufgabe 0: Git und GitHub kennenlernen**

*Lernziele: Commits, Branches, Push/Pull, Pull Requests, Code Review mit GitHub*

---

#### **📝 Aufgabenstellung**

Git und GitHub haben zwei Dimensionen, die du in dieser Aufgabe beide kennenlernen sollst:

| Dimension | Werkzeuge & Features |
|-----------|----------------------|
| **Lokal** (Visual Studio Code + Git) | Repository klonen (`clone`), Änderungen vormerken (`add`/`stage`), committen (`commit`), Branches erstellen und wechseln (`branch`, `checkout`/`switch`), Änderungen zusammenführen (`merge`), Konflikte lösen, Git-Integration in VS Code (Source-Control-Panel) |
| **Remote** (GitHub) | Änderungen hochladen (`push`) und herunterladen (`pull`/`fetch`), Pull Requests erstellen und reviewen, Issues anlegen und verfolgen, Code Review durch Copilot anfordern (GitHub Copilot Code Review), PR-Feedback von Lehrenden oder Agenten einarbeiten |

---

#### **🔧 Lokale Git-Arbeit mit Visual Studio Code**

1. **Repository klonen**

   - Öffne VS Code und klone dein GitHub-Classroom-Repository über *Source Control → Clone Repository* (Erscheint nur in einem leeren Fenster).
   - Alternativ im Terminal: `git clone <URL>`

2. **Feature-Branch erstellen**

   - Erstelle für jede Aufgabe einen eigenen Branch, z. B.:

     ```bash
     git switch -c feature/aufgabe-1-interfaces
     # -c steht für "create" – erstellt den Branch und wechselt sofort dorthin
     # Alternativ (ältere Syntax): git checkout -b feature/aufgabe-1-interfaces
     ```

   - Das hält den `main`-Branch sauber und ermöglicht später einen sauberen Pull Request.

```mermaid @mermaid
---
title: "Git-Workflow: Branching und Merging"
---
gitGraph
   commit
   commit
   branch develop
   checkout develop
   commit
   branch feature
   checkout feature
   commit
   checkout main
   merge feature
   checkout develop
   commit
   commit
   commit
   checkout main
   merge develop
   commit
   commit

```

3. **Änderungen committen**

   - Nutze aussagekräftige Commit-Nachrichten:

     ```bash
     git status                                        # Überblick: welche Dateien sind geändert?
     git add Himmelskoerper.cs IMissionsobjekt.cs      # gezielt einzelne Dateien vormerken
     git commit -m "feat: IMissionsobjekt Interface hinzugefügt"
     ```

   - Oder verwende das **Source Control Panel** in VS Code (Strg+Shift+G).

4. **Änderungen pushen**

   ```bash
   git push origin feature/aufgabe-1-interfaces
   ```

---

#### **🌐 Remote-Arbeit mit GitHub**

1. **Pull Request erstellen**

   - Öffne das Repository auf GitHub.
   - Klicke auf *Compare & pull request* für deinen Branch.
   - Beschreibe deine Änderungen im PR und wähle `main` als Zielbranch.

2. **Code Review von Copilot anfordern**

   - Im Pull Request: Klicke auf *Reviewers* → wähle **Copilot** aus.
   - Copilot analysiert deinen Code und gibt automatisch Feedback.
   - Arbeite das Feedback ein (neue Commits im selben Branch) und markiere Kommentare als erledigt.

3. **PR von Lehrenden reviewen**

   - Dein Lehrender oder ein Agent kann ebenfalls einen Review hinterlassen.
   - Lies die Kommentare, beantworte Fragen und passe deinen Code an.
   - Nach Freigabe wird der PR in `main` gemergt.

4. **Issues nutzen**

   - Erstelle ein Issue für einen Fehler oder eine Frage, z. B. *"Frage: Wie implementiere ich IEnumerable<T> korrekt?"*
   - Verweise in Commit-Nachrichten auf Issues: `fix: Validierung korrigiert, closes #3`

5. **Änderungen pullen**

   - Halte deinen lokalen `main`-Branch aktuell:

     ```bash
     git switch main
     git pull origin main
     ```

#### Aufgabenliste 00 

1. Clone dein Repository 

   - im Classroom die Aufgabe annehmen
   - im Repository die URL kopieren (grüner Button "Code")
   - im Terminal: `git clone <URL>` oder in VS Code: *Source Control → Clone Repository*
   - Wechsle in das geklonte Verzeichnis: `cd <repository-name>`

2. Erstelle einen Branch `integration`
3. Prüfe mit `git status`, welche Dateien unverändert bzw. geändert sind
4. Committe eine kleine Übungsänderung mit einer aussagekräftigen Nachricht
5. Push den Branch und erstelle einen Pull Request auf GitHub
6. Fordere einen Code Review von Copilot an und arbeite das Feedback ein
7. Merge den PR nach Freigabe nach `main`

### **🔌 Aufgabe 1: Interfaces für die Mission**

*Lernziele: Interface-Definition, Implementierung, Polymorphismus*

---

#### **📝 Aufgabenstellung**

Definiere das Interface `IMissionsobjekt`, das alle Objekte im Missionssystem beschreibt.

##### **🔧 Hilfestellungen**

**1. Interface `IMissionsobjekt` definieren**

```text @plantUML
@startuml
interface IMissionsobjekt {
  +Name : string
  +KatalogNummer : uint
  +GetStatusBericht() : string
}
@enduml
```

**2. Interface implementieren**

- Implementiere `IMissionsobjekt` in der abstrakten Klasse `Himmelskoerper`.
- Implementiere `GetStatusBericht()` in den Klassen `Stern`, `Planet` und `Mond`, um einen kurzen Statusbericht zurückzugeben.

  - Für `Stern`: *"Stern [Name] (Spektralklasse [Klasse]) mit Helligkeit [Helligkeit] mag"*
  - Für `Planet`: *"Planet [Name] umkreist Körper [KatalogNummerReferenz] in [Umlaufzeit] Jahren"*
  - Für `Mond`: *"Mond [Name] umkreist Körper [KatalogNummerReferenz] in [Umlaufzeit] Jahren"*

**3. Weiteres Interface `IVergleichbar<T>` definieren (mit Template)**

```text @plantUML
@startuml
interface IVergleichbar<T> {
    +VergleicheMit(T anderer) : int 
    +IstGroesserAls(T anderer) : bool 
    +IstKleinerAls(T anderer) : bool 
}
@enduml
```

- Implementiere `IVergleichbar<Himmelskoerper>` in `Himmelskoerper`, sodass Himmelskörper anhand ihrer `KatalogNummer` verglichen werden können.

<!-- class="lia-callout--note" style="width:100%" -->
> **💡 Bonusaufgabe – Operatorüberladung:**
> Wenn du `IVergleichbar<T>` implementiert hast, kannst du die gleiche Logik auch als überladene Operatoren anbieten.
> Füge dazu in `Himmelskoerper` statische Methoden hinzu, für:
>
> - `<` (Kleiner-als)
> - `>` (Größer-als)
> - `Equals` (Gleichheit)
> - `==` (Gleichheit)
> - `!=` (Ungleichheit)
> - `>=`, `<=` (optional)
> - `<=`, `>=` (optional)
>
> Damit kannst du statt `erde.IstGroesserAls(mond)` direkt `erde > mond` schreiben.
> Die Interface-Methoden bleiben die eigentliche Implementierung, die Operatoren sind nur **syntaktischer Zucker** darüber.

#### ✅ Testaufgabe

```csharp
IMissionsobjekt[] objekte = { sonne, erde, mond };
foreach (var obj in objekte)
{
    Console.WriteLine(obj.GetStatusBericht());
}

// Vergleich
Console.WriteLine(erde.IstGroesserAls(mond)); // false, da KatalogNummer 20001 < 30001
Console.WriteLine(sonne.VergleicheMit(erde));   // negativ, da 10001 < 20001
```

💡 Tipps
====================

- Ein Interface kann nicht instanziiert werden, definiert aber eine Vertragsstruktur.
- Eine Klasse kann mehrere Interfaces implementieren.
- `IComparable<T>` aus der .NET-Bibliothek funktioniert ähnlich wie `IVergleichbar<T>`.

### **🚀 Aufgabe 2: SpaceShip mit Unterklassen über IMissionsobjekt nutzen**

*Lernziele: Interface-Nutzung im Code, Polymorphismus, gemeinsame Verarbeitung unterschiedlicher Objekte*

---

#### **📝 Aufgabenstellung**

Erweitere das Missionssystem um eine neue Basisklasse `SpaceShip`, die ebenfalls das Interface `IMissionsobjekt` aus Aufgabe 1 implementiert.

Die Klasse `SpaceShip` dient als gemeinsame Basisklasse für verschiedene Raumschiffe. Leite davon mindestens zwei konkrete Unterklassen ab, damit sichtbar wird, warum ein Interface in einer Schleife oder einer Hilfsmethode nützlich ist.

##### **🔧 Hilfestellungen**

**1. Abstrakte Klasse `SpaceShip` einführen**

```text @plantUML
@startuml
interface IMissionsobjekt {
  +GetStatusBericht() : string
}

abstract class SpaceShip {
  +Name : string
  +KatalogNummer : uint
  +CrewGroesse : int
  +{abstract} GetStatusBericht() : string
  +ToString() : string
}

IMissionsobjekt <|.. SpaceShip
@enduml
```

- `SpaceShip` soll gemeinsame Eigenschaften aller Raumschiffe kapseln.
- Wie in Aufgabe 1 vorgegeben, gehört `GetStatusBericht()` dabei zum Vertrag von `IMissionsobjekt`.
- `GetStatusBericht()` bleibt abstrakt, damit jede Unterklasse ihren eigenen Bericht formuliert.
- `ToString()` soll in `SpaceShip` eine allgemeine Darstellung liefern, die von den Unterklassen erweitert oder überschrieben werden kann.

**2. Konkrete Unterklassen anlegen**

Leite mindestens zwei Klassen von `SpaceShip` ab, zum Beispiel:

- `CargoShip` mit einer Eigenschaft `LadungInTonnen`
- `ResearchShip` mit einer Eigenschaft `Forschungsgebiet`

Jede Unterklasse soll `GetStatusBericht()` und `ToString()` passend überschreiben.

Ein mögliches Klassendiagramm wäre zum Beispiel:

```text @plantUML
@startuml
interface IMissionsobjekt {
  +GetStatusBericht() : string
}

abstract class SpaceShip {
  +Name : string
  +KatalogNummer : uint
  +CrewGroesse : int
  +{abstract} GetStatusBericht() : string
  +ToString() : string
}

class CargoShip {
  +LadungInTonnen : float
  +GetStatusBericht() : string
  +ToString() : string
}

class ResearchShip {
  +Forschungsgebiet : string
  +GetStatusBericht() : string
  +ToString() : string
}

IMissionsobjekt <|.. SpaceShip
SpaceShip <|-- CargoShip
SpaceShip <|-- ResearchShip
@enduml
```

**3. Ausgaben**

**3.1 Interface gezielt nutzen**

Speichere Himmelskörper und Raumschiffe gemeinsam in einem Array oder in einer Liste vom Typ `IMissionsobjekt`.

So kannst du alle Objekte mit derselben Schleife verarbeiten, obwohl sie aus unterschiedlichen Klassenhierarchien stammen:

```csharp
// sonne, erde und mond wurden bereits in Aufgabe 1 erzeugt
IMissionsobjekt[] objekte = { sonne, erde, mond, cargoShip, researchShip };

foreach (var objekt in objekte)
{
    MissionsReport(objekt);
}
```

**3.2 Hilfsmethode `MissionsReport` für beliebige Missionsobjekte**

Die Methode `MissionsReport`, die ein beliebiges `IMissionsobjekt` entgegennimmt und sowohl die normale Objektausgabe über `ToString()` als auch den `StatusBericht` ausgibt, ist in `Program.cs` bereits vorgegeben:

```csharp
static void MissionsReport(IMissionsobjekt objekt)
{
    Console.WriteLine(objekt.ToString());
    Console.WriteLine(objekt.GetStatusBericht());
}
```

So wird deutlich, dass nicht der konkrete Typ wichtig ist, sondern nur der durch das Interface garantierte Vertrag.

#### ✅ Testaufgabe

```csharp
var cargoShip = new CargoShip("CargoMaster 3000", 50001, 5, 10000.0f);
var researchShip = new ResearchShip("Explorer X", 50002, 10, "Astrophysik");

static void MissionsReport(IMissionsobjekt objekt){
    Console.WriteLine(objekt.ToString());
    Console.WriteLine(objekt.GetStatusBericht());
}

IMissionsobjekt[] schiffe = { cargoShip, researchShip };
foreach (var obj in schiffe.Concat(objekte))
    MissionsReport(obj);
```

💡 Tipps
====================

- Ein Interface beschreibt, **was ein Objekt können muss**, nicht **von welcher Klasse es abstammt**.
- Durch `IMissionsobjekt` können `Planet`, `Mond`, `Stern` und `SpaceShip` gemeinsam verarbeitet werden.
- Die Basisklasse `SpaceShip` bündelt gemeinsame Eigenschaften, die Unterklassen ergänzen die Spezialisierung.
