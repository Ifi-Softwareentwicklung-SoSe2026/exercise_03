# Aufgabe: Vererbung und Interfaces mit Pflanzen

## Kontext
Im Ordner `exercise_code` liegt ein einfaches C#-Konsolenprojekt.

## Ziel
Erweitere die Modellierung von Pflanzen durch Vererbung und Interfaces.

## Aufgabenstellung
- Erstelle eine abstrakte Basisklasse `Plants` für gemeinsame Eigenschaften (z. B. Name, Alter).
- Erstelle zwei konkrete Klassen:
  - `AppleTree`
  - `Pumpkin`
- Nutze Vererbung, sodass beide Klassen von `Plants` abgeleitet sind.
- Definiere passende Interfaces für spezielles Verhalten, z. B.:
  - `ICookable` (für essbare Pflanzen)
  - `IWoodProducer` (für holzliefernde Pflanzen)
- Implementiere die Interfaces in den passenden Klassen.
- Erstelle mindestens ein Pflanzenobjekt, das **beide** Interfaces (`ICookable` und `IWoodProducer`) implementiert.
- Gib im `Program.cs` für mehrere Pflanzenobjekte aus:
  - Grundinformationen aus der Basisklasse
  - zusätzliches Verhalten über die Interfaces

## Akzeptanzkriterien
- Die Klassenhierarchie ist klar und korrekt.
- Mindestens zwei Interfaces sind definiert und sinnvoll eingesetzt.
- Mindestens eine konkrete Pflanzenklasse implementiert gleichzeitig `ICookable` und `IWoodProducer`.
- Das Projekt baut ohne Fehler (`dotnet build`).
- Beim Ausführen (`dotnet run`) ist die Ausgabe nachvollziehbar und zeigt die Interface-Fähigkeiten.
