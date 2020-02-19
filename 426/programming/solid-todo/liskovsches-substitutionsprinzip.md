# Liskovsches Substitutionsprinzip

{% hint style="info" %}
Das Liskovsche Substitutionsprinzip fordert, dass eine Instanz einer abgeleiteten Klasse sich so verhalten muss, dass jemand, der meint, ein Objekt der Basisklasse vor sich zu haben, **nicht durch unerwartetes Verhalten überrascht wird**, wenn es sich dabei tatsächlich um ein Objekt eines Subtyps handelt. 
{% endhint %}

## Ein Beispiel

Hier hat ein Entwickler den DistanceConverter "optimiert" indem er negative Werte welche er nicht braucht in positive umwandelt.

```php
<?php

class DistanceConverer
{
	  const FACTOR = 0.6214;
	  public static function milesToKilometers(int $miles ) : float
	  {
		return $miles / self::FACTOR;
	  }
}


class FormattingDistanceConverter extends DistanceConverer
{
	  public static function milesToKilometers(int $miles ) : float
	  {
			if ( $miles > 0){
				return $miles / self::FACTOR;
			}
			return -($miles / self::FACTOR);
	  }
}


echo DistanceConverer::milesToKilometers(20);
echo "<br>";
echo "<br>";
echo FormattingDistanceConverter::milesToKilometers(20);

```

Dies verstösst gegen das Liskovsches Substitutionsprinzip und muss vermieden werden! Die Parent-Klasse hat einen möglichen Wertebereich von Negativ-Float bis Positiv-Float. Bei der Child-Klasse wird der mögliche Wertebereich eingeschränkt.

* Das Einschränken von Return-Werten ist verboten
* Das Ändern von Return-Typen ist verboten

## Ein weiteres Beispiel

```php
class PostShipment
{
	  protected $cartTotalPrice;
	
	  public function __construct($cartTotalPrice){
		  $this->cartTotalPrice = $cartTotalPrice;
	  }
	
	  public function cost()
	  {
			return 0.0;
	  }
}

class PrimaryPostShipment extends PostShipment
{
	  public function cost()
	  {
		  	if($this->cartTotalPrice >= 5){
				return "Shipment is not allowed when the total card price is lower than 5";
			}
			
			// Free shipping when the total price is higher than 50
			if ( $this->cartTotalPrice > 50 ){
				return 0.0;
			}

			return 6.0;
	  }
}

class BudgetPostShipment extends PostShipment
{
	  public function cost()
	  {
			return 3.0;
	  }
}

$shipment = new PrimaryPostShipment(4);
echo $shipment->cost();

$shipment = new PrimaryPostShipment(50);
echo $shipment->cost();
```

