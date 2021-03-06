# SoftwareentwicklungSoSe2020_Aufgabe_04

## Bearbeitungzeit

2. Juni - 15. Juni 2020

## Idee der Übung

Das Aufgabenblatt adressiert die Grundlagen der Objektorientierten Programmierung unter C#. Dabei sollen Sie sich sowohl mit der spezifischen Semantik der Programmiersprache, aber auch den grundlegenen Konzepten zur Modellierung auseinander setzen.

## 1. Vererbung, Überschreiben von Elementen, dynamische Bindung, Indexer

1. Zu erstellen ist ein C#-Programm, das den Wissenschaftlern ermöglicht, die Merkmale einer infolge der Technoevolution entstandenen Spezies „Helmtiger“ im Vergleich zum bereits bekannten Tiger zu untersuchen. Erstellen Sie dazu die Klasse `Tiger`, die die Angaben zu
    
    + Registriernummer,
    + Schädelumfang (reelle Zahl) und
    + Schädelfestigkeit (ganze Zahl) enthält.

   Verwenden Sie dazu automatische Properties, die einen lesenden Zugriff erlauben, und zum Initialisieren der Felder sinnvolle Konstruktoren.

   Des Weiteren soll die Klasse die `ToString`-Methode von `System.Object` überschreiben, um die Ausgabe der Instanzen der Klasse zu erleichtern.

   Die ebenfalls zu erstellende Klasse `Helm` erhält die Angabe
    + zum inneren Durchmesser und ebenfalls
    + die Festigkeit.

   Ermöglichen Sie in der Klasse den lesenden Zugriff auf die Felder.

   Die Klasse `Helmtiger` ist von der Klasse `Tiger` abzuleiten.

   In der Klasse ist
      + ein weiteres Feld vom Typ der Klasse `Helm` zu definieren.

   Zum Zugriff auf das Feld von außerhalb der Klasse wird ein Property benötigt, das beim Zuweisen des Helms sicherstellt, dass „der Helm dem Tiger passt“, d.h., dass der Helmdurchmesser nicht kleiner als der aus dem Schädelumfang berechnete Wert ist, anderenfalls ist dem Helm-Feld der Wert `null` zuzuweisen.

   Eine weitere Methode der Klasse `Helmtiger` soll die Schädelfestigkeit des „behelmten“ Tigers als die Summe der Festigkeiten des Tigers und des Helms berechnen und zurückgeben.

   In der `Main`-Methode der Klasse `Register` ist zum Testen der Klassen ein Array aus Instanzen der Klassen `Tiger` und `Helmtiger` zu erstellen. Geben Sie alle Daten der im Feld gespeicherten Instanzen aus und, wo es möglich ist, die Gesamtfestigkeit.

2. Kennzeichnen Sie die Methode zum Berechnen der Gesamtfestigkeit als `virtual`-Methode. Passen Sie die Klasse `Tiger` und die `Main`-Methode der Klasse `Register` entsprechend an.

3. Passen Sie die Klasse `Register` so an, dass die Instanzen der Klassen `Tiger` und `Helmtiger` nicht in einem lokalen Array, sondern in einem Datenfeld der Klasse gespeichert werden.

   Definieren Sie zum Zugriff auf die Elemente des Arrays einen Indexer.

   Ein weiteres Property soll einen lesenden Zugriff das das gesamte Array erlauben.

   Die maximale Anzahl der Elemente des Arrays ist über ein optionales Argument des
   Konstruktors festzulegen.

   Ergänzen Sie die Klasse `Register` um eine Methode zum Suchen von Instanzen mit einer als Parameter übergebenen Registriernummer.

   Testen Sie die Methoden und Properties der Klasse `Register`, indem Sie die Elemente des Arrays mit Instanzen belegen, alle ausgeben bzw. einige suchen und ausgeben.

## 2. Überladene Operatoren, Klasse Object

Die Anwohner einer kleinen und kaum bekannten Insel haben ein eigenes Rechensystem mit folgenden Regeln entwickelt:

+ Jede Zahl wird durch eine entsprechende Anzahl von Stöckchen dargestellt.
+ Es gibt nur natürliche Zahlen (ganze Zahlen, die größer oder gleich Null sind).
+ Als Operationen beherrschen die Insulaner Addition, Subtraktion, Multiplikation und Division und die Vergleichsoperatoren kleiner, größer, gleich und ungleich.

Erstellen Sie eine Klasse, die eine Zahl dieses Rechensystems repräsentiert.

Intern soll die Zahl als eine ganze Zahl gespeichert werden, nach außen wird sie als ein String aus mehreren I-Buchstaben sichtbar. Beim Zuweisen des Strings ist zu überprüfen, ob die Zechenkette tatsächlich nur I-Zeichen enthält, anderenfalls ist eine `FormatException` auszuwerfen.

Definieren Sie in der Klasse die Operatoren `+`, `-`, `*` und `/`. Beachten Sie beim
Minusoperator, dass es keine negativen Zahlen gibt, und beim Divisionsoperator, dass
es keine gebrochenen Zahlen gibt.

Definieren Sie die Vergleichsoperatoren `<`, `>`, `==` und `!=`.

Ergänzen Sie die Klasse um die von der Klasse `Object` vererbten, überschriebenen Methoden `ToString`, `Equals` und `GetHashCode`.

Testen Sie die überladenen Operatoren und Methoden in der `Main`-Methode.

## 3. Entwurfsprozess

Ihr Team entwirft ein Modell, dass verschiedene Smartphone-Typen mit unterschiedlichen Betriebssystemen abbildet. Dabei wird davon ausgegangen, dass alle Mobiltelefone gleichermaßen folgende Elemente umsetzen:

| Membertyp   | Name          | Type       | 
|:------------|:--------------|:-----------|
| Eigenschaft | `PhoneNumber` | `string`   |
|             | `PhoneState`  | `enum{off, on, unknown}` |
|             | `ConnectionState`| `enum{connected, offline}` |
| Methoden    | `makeACall(string phoneNumber)` |             | 
|             | `receiveACall(string incommingNumber)` |      | 
|             | `getOS()`           |  |

Daneben gibt es betriebssystemspezifische Implementierungen von Nutzerkennungen (`AppleId` vs. `Google Account`) oder aber Methoden für die unterschiedlichen App-Stores. Für die Android-Geräte ist die Situation noch komplexer. Hier integrieren die verschiedenen Hersteller häufig eigene Implementierungen, wie zum Bespiel für die Lokalisierung des Gerätes. Ihr Modell sollte also auch eine `RunVendorSpecificLocalization()` für unterschiedliche Marken enthalten.

Entwerfen Sie eine Interface/Klassenhierachie, die diese Aspekte abbildet. Sie können dafür auf unterschiedlichen Wegen vorgehen.

1. Sie implementieren Ihren Entwurf in C# und generieren den zugehörigen PlantUML Code daraus. Hierfür wurde eine GitHub-Action angelegt, die Ihren Code in `Aufgabe_3/main.cs` parst und daraus den plantUML Code  `Aufgabe_3/main.plum` generiert und daraus ein Diagramm im png Format erzeugt (siehe [Link auf Action](https://github.com/ComputerScienceLecturesTUBAF/SoftwareentwicklungSoSe2020_Aufgabe_04/blob/master/.github/workflows/generate_UML_from_Csharp.yml)).

2. Sie halten Ihren Entwurf direkt in PlantUML fest. Dazu exisitiert eine Datei `Aufgabe_3/main.cs`, die dann automtisch in ein png überführt wird (siehe [Link auf Action](https://github.com/ComputerScienceLecturesTUBAF/SoftwareentwicklungSoSe2020_Aufgabe_04/blob/master/.github/workflows/generate_UML_from_plum.yml)).

Fügen Sie in das PlantUML File gern Dokumentationshinweise ein, die dem Leser helfen Ihre Designidee zu verstehen. Die PlantUML Dokumentation finden Sie für Klassendiagramme unter [https://plantuml.com/de/class-diagram](https://plantuml.com/de/class-diagram)
