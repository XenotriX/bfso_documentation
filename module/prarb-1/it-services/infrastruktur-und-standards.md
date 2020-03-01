# Infrastruktur und Standards

## IT-Services

Beliebige Dienstleistung in der Informatik

* Beratung
* Planung
* Ausführung
* Im Prinzip Produkte, welche verkauft werden

### SLA

Service Level Agreements

* Abmachungen mit einem IT-Partner über Support und Updates
* z.B. 4 Stunden wöchentlich, Updates und Monitoring inklusive \[..\] 

### SOA

Serviceorientierte Architektur - Verteilte Services welche von einem/oder mehreren Anbieter bereit gestellt werden und von Anwendern jederzeit verwendet werden können.

* AWS
* Kreditwürdigkeit für einen Webshopbetreiber
* Google Maps

### Web-Services

* REST
* SOAP
  * WSDL
* XML-RPC
* GraphQL

### Prinzipien der IT-Industrialisierung

* Standardisierung
* Automatisierung
* Modularisierung
* Kontinuierliche Verbesserung
* Konzentration auf die Kernkompetenzen

### Standardisierung von Prozessen

* Aquirierung eines Projekts
* Workshop mit dem Kunden
* Kundenkontakt
* Umsetzung des Projekts
* Dokumentation des Projekts
* Testen 
* Qualitätssicherung
* Deployment
* CI

### Standardisierung innerhalb der Firma

* Wie wird die Zeit erfasst?
* Wie kann man seine Überzeit kompensieren?
* Was muss getan werden bei einem neuen Mitarbeiter?
  * PC einrichten
  * Lizenzen lösen
  * Logins erstellen
  * Mailkonto erstellen
  * In der Lohnbuchhaltung erfassen
  * usw.
* Was muss getan werden bei einer Kündigung?
  * Zugangsdaten löschen
  * Schlüssel abgeben
  * Lohnzahlungen stoppen
  * usw.

### Standardisierung durch Virtualisierung

* Verteilung von virtuellen vordefinierter Entwicklungsumgebungen

### Kontinuierliche Verbesserung

Script. S.9

### Internationalisierung

1. Binnenorientierung
   * Kleine und mittlere Unternehmen
   * Nationale und regionale Märkte
2. Follow the Customer
   * Mittelgrosse Unternehmen
   * Geschäftsaktivitäten als Reaktion auf Kundenanforderungen
   * Produkt wächst mit den Kundenanforderungen
3. Ausdifferenzierung der Produktionsstrukturen
   * Internationale Produktion und Partnerbeziehungen
   * Ziel: Kosteneinsparungen durch Offshoreing und Nearshoring
4. Global integriertes Unternehmen
   * Erzeugen ein Grossteil des Umsatzes im Ausland

## Wissen

### Wissensmanagement

* 3 Stunden für die Lösung eines Problems
* 5 Minuten um die Lösung zu notieren
* Falls die Lösung nicht dokumentiert ist, verliert der nächste Mitarbeiter wieder 3 Stunden
* Regelmässiges Sortieren und Ausmisten der Wissensdatenbank 
* Definition von Regeln zu Erfassung von Wissensbeiträgen
* Bewerten von Beiträgen nach Relevanz
* Tagging 
* Wissensmanagement bezeichnet das Planen, Organisieren, Koordinieren und Kontrollieren der Ressourcen Information und Wissen. Es zielt darauf ab das intellektuelle Kapital eines Unternehmens erfassbar und transferierbar zu machen.

### Wissenstransfer

* Informiere deine Mitarbeiter bei neuen Erkenntnissen, Technologien und Problemlösungen \(Chat, Intranet\)
* Bereitstellen von Wissensinhalten an Kunden auf der Webseite
  * Content
  * Kundenbindung
  * SEO
* Wöchentliche interne Schulungen
  * Verkürzung der Einarbeitungszeit

### Data Warehousing

* Data Warehousing bezeichnet eine zentrale Datensammlung, deren Inhalt sich aus unterschiedlichen Quellen zusammensetzt
* Datenanalyse als Basis für betriebswirtschaftliche Entscheidungen

### Big Data

* Social Media für Pharmaprodukte
  * Data Mining von spiegelonline.ch

### Tagging

* Möglichkeit zur Priorisierung von Informationen
* Siehe [https://stackexchange.com/sites](https://stackexchange.com/sites)
* Das Internet ist eine Wissensdatenbank
* gidf!

## SOA @todo

Beispiel Kartenverlag

* Lese Lektion 2 SOA

### Was ist SOA?

* Stellt Services in den Mittelpunkt
* Ein Service ist eine Dienstleistung
* Ein Service kann in einem Satz zusammengefasst werden, z.B.:
  * "Der Service stellt interaktive Karten zur Verfügung"
  * "Der Service erlaubt das Übersetzen von Text"
* Klar stellt Google Maps mehr Funktionen zur Verfügung, Weg-Berechnung, Suchen von Restaurants usw. Es ist aber definitiv kein Tool zum Übersetzen von Text. Das hätte da nichts verloren.

### Services als Konstruktionsprinzip

* SOA Organisationen betreiben Services, keine Anwendungen und sie nutzen Services und keine Komponenten.
  * Das in der Theorie, in Wirklichkeit gibt es das natürlich nicht
  * Jede Firma betreibt aus Kostengründen monolithische Standardsoftware

### Lose Kopplung

* Services sollen im Interesse der Flexibilität und Modifizierbarkeit so unabhängig wie möglich und nur so abhängig wie nötig sein
* Es gibt verschiedene Arten von Abhängigkeiten
  * Zeitliche Abhängigkeit
  * Örtliche Abhängigkeit
  * Datenabhängigkeit

### Trennung von Schnittstelle und Implementierung

* Services werden den Nutzern über fest definierte Schnittstellen zur Verfügung gestellt
* Nach Aussen hin ist die Schnittstelle sichtbar, die Implementierung bleibt verborgen

Weiter auf Seite 27 @todo

