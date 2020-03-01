# IP

### Aufgaben

* Low level - Schickt das Paket an den richtigen Computer.
* 192.168.1.1

### **Subnetmask**

* 255.255.0.0

### **Internet-Adressklassen**

* A, B, C, D, E, F

### **IP v.6**

@todo

### **Ist Zustand**

* IP-Adresse: 192.168.0.1
* 1 Subnetz
* Subnetz Maske: 255.255.255.0
* Klasse C Netzwerk

| **Netzanteil** | **Hostanteil** |
| :--- | :--- |
| 192.168.0. | 1 |
| 255.255.255. | 0 |

**Aufgabe**

* Unterteile das aktuelle Subnetz in 6 Subnetze
* Wie viele Hosts können pro Subnetz verwendet werden
* Wie lautet die Adresse des ersten Subnetzes?

#### Netzadresse und Subnet in Binär:

| Netzanteil | **Hostanteil** |  |  |
| :--- | :--- | :--- | :--- |
| 192. | 168. | 0. | 0 |
| 1100 0000 | 1010 1000 | 0000 0000 | 0000 0000 |
| 255. | 255. | 255. | 0 |
| 1111 1111 | 1111 1111 | 1111 1111 | 0000 0000 |

**Anzahl Mögliche Subnetze**

| Bits | 1 | 2 | **3** | 4 | 5 | 6 | 7 | 8 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Anzahl der möglichen Subnetze | 2 | 4 | **8** | 16 | 32 | 64 | 128 | 256 |

* Bei 6 gewünschten Subnetzen werden 8 Subnetze genommen
* Für 8 Subnetze werden 3 Bits benötigt

| Neuer Netzanteil | **Hostanteil** |  |  |  |
| :--- | :--- | :--- | :--- | :--- |
| 192. | 168. | 0. | 0 |  |
| 1100 0000 | 1010 1000 | 0000 0000 | 000 | 0 0000 |
| 255. | 255. | 255. | 224 |  |
| 1111 1111 | 1111 1111 | 1111 1111 | 111 | 0 0000 |

**Wie viele Adressen stehen pro Subnetz zur Verfügung?**

* Hostanteil besteht aus 5 Bits
* Das Netz bekommt 1 Bit
* Die Broadcastadresse bekommt 1 Bit
* `2^5 - 2 = 30` Host pro Subnet 

**1. Subnetz**

| Subnetzadresse |  |  |  |
| :--- | :--- | :--- | :--- |
| 192. | 168. | 0. | 0 |
| Adressbereich |  |  |  |
| 192. | 168. | 0. | 1 |
| 192. | 168. | 0. | 30 |
| Broadcast |  |  |  |
| 192. | 168. | 0. | 31 |

**Zusatzaufgabe** - Ergänze folgende Tabelle

| Subnet Mask | Anzahl Unternetze | Nutzbare Hosts pro Subnet |
| :--- | :--- | :--- |
| 255.255.255.0 | 1 | 254 |
| 255.255.255.128 | 2 | 126 |
| 255.255.255.192 |  |  |
| 255.255.255.\[ \] | 8 | 30 |
| 255.255.255.\[ \] | 32 |  |

