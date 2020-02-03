# DNS

### Aufgaben

* Telefonbuch für das Internet
* Übersetzt IP-Adressen zu einfach lesbaren Domain-Namen
* 300 Millionen Domains sind aktuell registriert

| Level | Beispiel |
| :--- | :--- |
| Top Level Domains | .ch .com |
| Second Level Domains | google.com |
| Sub-Domain | images.google.com |

**Ablauf eines Zugriffs auf die URL** `https://google.com/images`

1. **DNS Lookup**
2. DNS Server
   * Gibt die IP-Adresse zurück
3. **PC macht eine TCP Verbindung zu einem Webserver**
4. Standardmässig auf dem PORT 80
5. **Mittels des Protokolls HTTP wird ein GET Befehl an den Webserver geschickt**
6. Falls die Seite existiert, sendet der Webserver ein HTML Dokument mit dem Statuscode 200 \(OK\) zurück
7. Es gibt noch weitere Statuscodes wie etwa `404`, `503` oder `500`

#### DNS Records

| Code | Art | Beschreibung |
| :--- | :--- | :--- |
| A | IPv4 Address |  |
| AAAA | IPv6 Address |  |
| MX | MailboX | Zu A Record mappen  Server The Mail Server  MX Level Priorität  TTL Sekunden im Cache |
| CNAME | Canonical Name Record  Alias Record Name | Damit mehrere Servertypen \(HTTP, FTP\) mit derselben IP laufen können Damit man die IP für mehrere Einträge gleichzeitig ändern kann |

TTL

* Wenn du eine statische IP hast sollte das TTL über 1800 sein
* Bei einer dynamischen IP sollte das TTL unter 1800 sein
* Idealerweise ein paar Stunden vor einem Wechsel das TTL verkleinern

MX - Beispiel

| NAME | TTL | TYPE | DATA | MX LEVEL |
| :--- | :--- | :--- | :--- | :--- |
| mail1.example.com | 1800 | A | 192.168.1.2 |  |
| example.com | 1800 | MX | mail1.example.com | 10 |

AAAA

* [https://mxtoolbox.com/IPv6.aspx](https://mxtoolbox.com/IPv6.aspx)

