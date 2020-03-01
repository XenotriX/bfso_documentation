# Windows 10

## Geschichte

* Ursprünglich ein grafisches Interface für DOS

## Windows 10 Versionen

In Zukunft wolle man keine neuen Versionen mehr veröffentlichen; stattdessen sehe man „Windows als eine Dienstleistung“

* 1803 April 2018
* 1809 Oktober 2018
* 1903 Mai 2019

#### Kennzeichen

* 32‐ oder 64‐Bit‐Architektur mit Multitasking, Multiprocessing und Multiuser‐Unterstützung

  Stabilität und Kompatibilität

* Sicherheit und ein leistungsfähiges Dateisystem
* breite Hard‐ und Softwareunterstützung
* "benutzerfreundliche" Bedienung

## **Preemptives Multitasking**

**Multitasking** bedeutet, dass mehrere Anwendungen nebeneinander auf demselben Prozessor laufen können. Das Betriebssystem erteilt den Anwendungen nacheinander – je nach Priorität und Verfügbarkeit – Prozessorzeit. 

**Preemptives Multitasking** bedeutet, dass die Kontrolle über einen Prozess immer beim Betriebssystem bleibt. Der Prozess bekommt einen separaten Speicherraum zur Verfügung gestellt, erhält aber nicht die Kontrolle über den Prozessor. Dadurch kann er auch bei einem Fehler nicht das gesamte Betriebssystem zum Absturz bringen.

## Hardware Abstraction Layer \(HAL\)

Alle Zugriffe von Anwendungen auf die Hardware, werden vom Betriebssystem kontrolliert. Anwendungen, die direkte Hardwarezugriffe erfordern \(z. B. einige Spiele und Tools\), können deshalb seit Windows XP nicht mehr ausgeführt werden. Auch der Betriebssystemkern \(Kernel\)  greift nicht direkt auf die Hardware zu. Zwischen dem Kernel und der Computerhardware, befindet sich eine Schicht, die als Hardware Abstraction Layer \(HAL\)  bezeichnet wird und Hardwarezugriffe vermittelt. Eine direkte Kommunikation von Gerätetreibern \(wie z. B. Grafiktreibern mit der Hardware\) ist aus Kompatibilitätsgründen zwar weiter möglich, es stehen dann allerdings nicht alle Grafikfunktionen von Windows zur Verfügung. Auch im neuen WDDM \(Windows Display Driver Modell\) sind Direktzugriff auf die Hardware verboten. Der Hersteller der Grafikkarte muss einen entsprechend ange‐ passten Treiber anbieten, um den vollen Leistungsumfang der Windows Grafikfunktionen auszuschöpfen.

