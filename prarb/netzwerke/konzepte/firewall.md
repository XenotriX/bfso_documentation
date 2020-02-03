# Firewall



**Aufgaben**

* Trennung zwischen zweier Netzwerkbereichen
* Kontrollierte Weiterleitung von Paketen
* Pakete werden auf Inhalt und Ziel kontrolliert

**Anforderungen**

* Der Quellcode der Firewall muss sichtbar sein
  * Open Source
* Muss auf einem minimalistischen System laufen \(linux\)
* Keine andere Software auf demselben Gerät \(z.B. Telefonsoftware\)

**Regeln**

* Protokolle
* Netzwerk-Zonen
* Ports
* Port-Forwarding
* IP-Adressen

**Regeln für LAN**

* ERP-Server
  * Externer Partner greift auf den Server zu, um Updates zu machen
    * Port 3389, TCP ist offen
    * maximal eine Verbindung
* Daten-Server
  * Von einem externen Rechenzentrum wird auf Daten zugegriffen
    * Port 22, TCP
    * Von einer spezifischen IP
    * inbound \(Verbindung wird von Aussen nach Innen aufgebaut\)
* HTTPS
  * Mitarbeiter dürfen auf Webseiten
    * HTTPS, Port 443, TCP outbound, für alle 

