# Open-Closed-Prinzip

{% hint style="info" %}
* Module \(Klassen, Methoden\) sollten sowohl **offen** \(für Erweiterungen\), als auch **geschlossen** \(für Modifikationen\) sein.
* Erweitere die Funktionalität indem du neunen Code hinzufügst statt bestehenden Code zu bearbeiten
* Teile die Funktionalitäten so auf, dass das System einfach erweitert werden kann, aber nie kaputt geht.
{% endhint %}

Eine Erweiterung im Sinne des **Open-Closed-Prinzips** ist beispielsweise die **Vererbung**. Diese **verändert** das vorhandene Verhalten einer Klasse **nicht**, **erweitert sie aber** um zusätzliche Funktionen oder Daten. Überschriebene Methoden verändern auch nicht das Verhalten der Basisklasse, sondern nur das der abgeleiteten Klasse.

## Ein Beispiel:

#### Ausgangslage

```php
<?php

namespace App\Shop\Payment;

class Payment
{
    public function pay($type){
        if($type == 'paypal')
        {
            echo "payWithPayPal";
        }
        if($type == 'creditcard')
        {
            echo "payWithCreditCard";
        }
    }
}
```

Implementation gemäss Open/Closed





