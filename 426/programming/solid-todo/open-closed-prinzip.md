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

{% code title="app/Http/Controllers/CheckoutController.php" %}
```php
public function pay(Request $request){
    $payment = new Payment();
    $payment->pay($request->payment_type);
}
```
{% endcode %}

#### Implementation gemäss Open/Closed

{% code title="app/Shop/Payment/PaymentInterface.php" %}
```php
<?php

namespace App\Shop\Payment;

interface PaymentInterface
{
    public function pay();
}
```
{% endcode %}

{% code title="app/Shop/Payment/PaymentFactory.php" %}
```php
<?php

namespace App\Shop\Payment;

class PaymentFactory
{
    public function createPayment($type){
        if($type == 'paypal')
        {
            return new PayPalPayment();
        }
        if($type == 'creditcard')
        {
            return new CreditCardPayment();
        }
    }
}
```
{% endcode %}

{% code title="app/Shop/Payment/CreditCardPayment.php" %}
```php
<?php

namespace App\Shop\Payment;

class CreditCardPayment implements PaymentInterface
{
    public function pay() {
        echo "payWithCreditCard";
    }
}
```
{% endcode %}

{% code title="app/Http/Controllers/CheckoutController.php" %}
```php
public function pay(Request $request){
    $paymentFactory = new PaymentFactory();
    $payment = $paymentFactory->createPayment($request->payment_type);
    $payment->pay();
}
```
{% endcode %}

#### Vorteile

Auch wenn die Implementation auf den ersten Blick komplizierter erscheid. So zeigen sich die Vorteile sobald das Programm komplizierter wird. Müsste man zum Beispiel die Kreditkartenzahlung anpassen so müsste nur das File `app/Shop/Payment/CreditCardPayment.php` angepasst werden. Alle anderen Zahlungsmethoden müssten nicht berührt werden und somit auch nicht getestet werden. 

Auch wenn man eine neue Zahlungsmethode hinzufügen will - muss man nur ein neues File z.B. `app/Shop/Payment/TwintPayment.php` hinzufügen \(und die Factory ergänzen\). So muss man sich keine Sorgen um die bestehenden Zahlungsmethoden machen.   

{% embed url="https://github.com/bfso/426\_gourmet-webshop/blob/feature/payment/app/Http/Controllers/CheckoutController.php" %}



