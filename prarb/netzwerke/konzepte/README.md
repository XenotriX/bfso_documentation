# Konzepte

## Netztopologien

* Bus-Topologie
* Baum-Topologie
* Stern-Topologie
* Dezentrale-Topologie
  * The Internet

## Host-Architekturen

#### Client-Server

* Server übernimmt rechenintensive Prozesse
* Server hat zentrale Datenhaltung
* Das Internet basiert auf der Client-Server-Architektur

#### Peer to Peer

* zum Beispiel `torrent`

## Datenübertragung

#### Unicast

* Punkt zu Punkt Verbindung ohne Zwischenstationen

#### Broadcast

* Gleichzeitig zu allen im Netz angeschlossenen Rechnern
* Network Discovery

#### Multicast

* Senden von Daten an mehrere Rechner
* Oft mit Hilfe von virtuellen Netzen

## Netz-Dienstleister

#### Carrier

* Stellt die Leitungen zur Verfügung
* Backbone

#### Internet Service Provider \(ISP\)

* Verkaufen Dienstleistungen an die Endkunden
* Internetzugang
* Swisscom, Cabelcom, Init7

#### Autonome Systeme

* Jeder ISP bekommt ein Liste mit IP-Adressen zur Verfügung gestellt. Diese IP-Adressen können an die Endkunden weiter gegeben werden. Der ISP wird mit einer **AS Nummer** identifiziert. Die AS Nummer stellt das Netzwerk nach Aussen hin dar.

#### Peering

* Datenaustausch zwischen Netzbetreibern und Netzwerken

## Netzwerktechnologien

#### IEEE 802

| 802.3 | Ethernet | 1Gbit/s \(Kupfer\) 400Gbit/s \(Glasfaser\) |
| :--- | :--- | :--- |
| 802.11 | WLAN | 800-1700 Mbit/s \(802.11ac\) |

## WLAN

WLAN arbeitet auf der Bitübertragungsschicht, Schicht 1 des OSI-Schichtenmodells und ist Protokoll-unabhängig.

{% hint style="warning" %}
WPA verwenden!
{% endhint %}

## VLAN

* Beim **virtuellen Routing** \(dynamisches VLAN\) leistet der Router oder der Switch die Zuordnung mittels einer Management Datenbank.
* Abschottung sicherheitsrelevanter Abteilungen \(z.B. Buchhaltung\)
* Abschottung von Druckernetzwerken \(Drucker melden automatisch falls der Füllstand leer ist\)
* VLANs haben den Vorteil, dass man logische Strukturen eines Netzwerks verändern kann ohne Kabel umstecken zu müssen
* Script S.55

