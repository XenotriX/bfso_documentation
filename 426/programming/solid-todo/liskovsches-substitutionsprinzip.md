# Liskovsches Substitutionsprinzip

{% hint style="info" %}
Das Liskovsche Substitutionsprinzip fordert, dass eine Instanz einer abgeleiteten Klasse sich so verhalten muss, dass jemand, der meint, ein Objekt der Basisklasse vor sich zu haben, **nicht durch unerwartetes Verhalten überrascht wird**, wenn es sich dabei tatsächlich um ein Objekt eines Subtyps handelt. 
{% endhint %}

## Ein Beispiel

```php
<?php

class DistanceConverer
{
	  const FACTOR = 0.6214;
	  public static function milesToKilometers( $miles )
	  {
		return $miles / self::FACTOR;
	  }
}


class FormattingDistanceConverter extends DistanceConverer
{
	  public static function milesToKilometers( $miles )
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



