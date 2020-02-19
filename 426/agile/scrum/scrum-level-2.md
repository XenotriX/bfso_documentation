# Scrum - Level 2

## Unsicherheiten

* Unsicherheiten sollen identifiziert und behoben werden

### Entscheidungen sollten erst im letzten vernünftigen Moment getroffen werden

Wenn man Entscheidungen so spät als möglich trifft hat man folgende Vorteile:

* Man hat **weniger Unsicherheiten** da mehr Wissen zum Projekt da ist
  * Wahrscheinlichkeit dass man eine falsche Entscheidung trifft ist **kleiner**

![](../../../.gitbook/assets/lrm.png)

## User Stories

* Eignen sich nicht für alle Backlog-Elemente welche ausgeführt werden sollen
  * "Als Kunde hätte ich gerne dass das System nicht die Datenbank beschädigt" wäre z.B. ein solcher Task welcher sich nicht gut als User-Story ausdrücken lässt
* Eignen sich gut um einen gewünschten Geschäftswert oder eine Business-Anforderung auszudrücken

#### User Story Vorlage

* Als &lt;Benutzerrolle&gt; möchte ich &lt;Ziel&gt;, so dass &lt;Vorteil&gt;

> Als **Wiki-Benutzer** möchte ich eine **Datei in das Wiki laden**, so dass ich sie mit meinen Kollegen teilen **kann**.

**Zufriedensheitsbedingungen**

Oft ist es sinnvoll zu einer User-Story einige Punkte zu definieren ab wann die Aufgabe als abgeschlossen gilt

> * Nur Dateien mit der Dateiendung jpg und png dürfen hochgeladen werden
> * Nur Dateien kleiner als 100 Megabyte dürfen hochgeladen werden
> * Nur wenn der User mehr als 39 Wiki-Punkte hat, darf er Dateien hochladen

#### Es lohnt sich in gute User-Stories Zeit zu investieren

Folgende Kriterien sollte eine User-Story erfüllen

* Independent
  * Stories sollten nicht von zu vielen anderen Stories abhängig sein.
* Negotiable
  * Stories sind keine Verträge, sie dienen vielmehr als Grundlage für Gespräche.
  * Bei Stories geht es um das WAS und WARUM, nicht um das WIE.
* Valuable
  * Wenn eine Story weder für den Kunden noch für den Anwender von Wert ist - so gehört sie nicht in den Backlog.
* Estimatable
  * Sollte ein Team eine Story nicht schätzen können, dann ist die Story zu gross oder es gibt zu viele unbekannte Faktoren.
* Small
  * Man will während eines Sprints an mehreren Stories arbeiten können, nicht nur an einer Story.
* Testable
  * Wenn man gute Zufriedenheitsbedingungen definiert kann man beim Abschluss einer Story genau testen ob die Story erfüllt wurde.

#### Stories zum Wissenserwerb

Man kann Stories erstellen die dem Erwerb von Wissen dienen. Dieser Vorgang kann verschiedene Namen haben: Prototyp, Studie, Spike. Oft wollen wir so erfahren ob eine Idee technisch möglich ist.

## Technische Schulden

> Software zu schreiben ist wie Schulden aufnehmen. Geringe Schulden aufzunehmen beschleunigt die Softwareentwicklung, solange die Schulden rasch durch eine Neuimplementierung getilgt werden… Die Gefahr entsteht, wenn die Schulden nicht zurückgezahlt werden. Jede Minute, die man mit nicht ganz richtigem Code verbringt, zählt als Zins auf diese Schuld. Ganze Entwicklungseinrichtungen können unter der Schuldenlast einer unbereinigten Implementierung zum Stillstand gebracht werden. . 
>
> Ward Cunningham

Wenn man technische Schulden hat, verkümmert das Produkt immer wie mehr und die Änderungskosten werden grösser.

* Frust bei Entwicklern wird grösser
* Kundenzufriedenheit sinkt
* Technische Schulden sollten überwacht werden - so wird dem Management oder dem Kunden klar was es bedeutet wenn man die Produktentwicklung beschleunigt.

#### Abbauen von Schulden

* Schulden sind abzubauen sobald man ihnen begegnet \(Pfadfinderregel\)
* Schulden sind Schrittweise abzubauen
* Schulden abbauen während man für den Kunden werthaltige Arbeit erledigt
* Schulden müssen nicht abgebaut werden falls:
  * Das Produkt sich dem Ende seiner Lebensdauer nähert
  * Es sich um einen Prototyp handelt



