# UDP-TCP

### UDP

Aufbau eines UDP-Pakets:

| IP HEADER | PAYLOAD |  |
| :--- | :--- | :--- |
| IP Adresse | UDP HEADER | PAYLOAD |
|  | PORT = CHECKSUM = | DATA |

* Skype verwendet den **PORT 3478**
* Der PC gibt ein Paket an dasjenige Programm weiter, welches sich für einen PORT angemeldet hat. \(Wie bei einem Postfach\)
  * Solange die Firewall es nicht verhindert
* Mit der Checksumme kann kontrolliert werden ob ein UDP-Paket korrekt ist
* UDP hat keine Möglichkeit Fehler zu korrigieren oder neue Pakete anzufordern, fehlerhafte Pakete werden verworfen
* Schnell, mit Verlusten wird gerechnet
* Games
* Videochat

### TCP

Aufbau eines TCP/IP Pakets:

| IP HEADER | PAYLOAD |  |
| :--- | :--- | :--- |
| IP Adresse | TCP HEADER | PAYLOAD |
|  | SEQUENCE NUMBER =  PORT =  | DATA |

![1538466415101](C:\Privat\Berufschule%20Visp\1538466415101.png)

* Mehrere Pakete können gleichzeitig gesendet werden

**Was ist der wesentliche Unterschied zwischen TCP und UDP?**

**Wozu wird UDP verwendet?**

**Würdest du für Whatsapp UDP oder TCP verwenden?**

**Auf welchem Port ist ein Webserver erreichbar?**

