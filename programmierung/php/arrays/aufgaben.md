# Aufgaben Arrays - 1

## Summe von Array-Werten

```php
	funtion sum($table){
		    $sum = 0;
        // do important stuff here
        return $sum;
	}
	
	$table = [
        [1,2],
        [3,4,5]
	];
	echo sum($table);
```

## Summe von Array-Werten

Ergänze folgenden Code damit die Rekursion funktioniert \(Das Resultat muss `8` sein, da `8` mal die `1` zusammengezählt werden soll\)

```php
function sum($array){
      $sum = 0;
      foreach($array as $item){
            if(is_array($item)){
                  $sum += sum($item);
                  echo $sum."<br>"
            }else{
                  $sum += $item;
            }
      }
      return $sum;
}

$table = [
      [1,1],[2,2,[[3,3],4,4]]
];
echo sum($table);
```



