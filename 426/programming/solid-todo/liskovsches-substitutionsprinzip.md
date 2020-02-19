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

