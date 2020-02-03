# Arrays

```php
<?php
      // Array mit Integer-Werten
      $numbers = [10, 20, 30, 40];

      // Array mit Varchar-Werten (Strings)
      $numbersAsStrings = ["eins", "zwei", "drei"];

      // Arrays können mit einer foreach-Schlaufe durchgegangen werden
      foreach ($items as $item) {
            echo $item . " <br>";
      }

      // Array-Elemente haben immer einen Schlüssel welcher das Element eindeutig identifiziert
      foreach ($items as $key => $item) {
            echo "Das Element mit dem Schlüssel " . $key . " hat den Inhalt '" . $item . "'<br>";
      }

      // Standartmässig sind die Schlüssel durchnummeriert
      $array = [
            1 => "eins",
            2 => "zwei",
            3 => "drei"
      ];

      // Die Schlüssel (Keys) können auch selber definiert werden
      // "a" ist der Schlüssel (Key), "eins" ist der Wert (Value)
      // "b" ist der Schlüssel (Key), "zwei" ist der Wert (Value)
      $array = [
            "a" => "eins",
            "b" => "zwei"
      ];

      // Array-Elemente können wiederum Arrays sein
      // Dies nennt man mehrdimensionale Arrays
      $items = [
            [1, 2, 3],
            [4, 5, 6],
            [7, 8, 9]
      ];

      // Auch bei diesen mehrdimensionalen Arrays kann man die Schlüssel selber definieren
      // 1 ist der Schlüssel, ['firstname' => 'hans', 'lastname' => 'muster'] ist der Wert
      $persons = [
            1 => ['firstname' => 'hans', 'lastname' => 'muster'],
            2 => ['firstname' => 'laura', 'lastname' => 'meier'],
      ];

      // Möchte man mehrdimensionale Arrays ausgeben hat man 2 Möglichkeiten
      // 1: Indem man auf den Index zugreift
      foreach ($persons as $person) {
            echo $person['firstname'] . " " . $person['lastname'] . " <br>";
      }
      // 2: Oder mittels 2 Foreach-Schlaufen
      foreach ($persons as $personValues) {
            foreach ($personValues as $value) {
                  echo $value . " ";
            }
            echo "<br>";
      }
```

#### I have an array of subarrays in the following format

```php
[
    'a' => [ 'id' = 20, 'name' = "chimpanzee" ],
    'b' => [ 'id' = 40, 'name' = "meeting" ],
    'c' => [ 'id' = 20, 'name' = "dynasty" ],
    'd' => [ 'id' = 50, 'name' = "chocolate" ],
    'e' => [ 'id' = 10, 'name' = "bananas" ],
    'f' => [ 'id' = 50, 'name' = "fantasy" ],
    'g' => [ 'id' = 50, 'name' = "football" ],
]
```

And I would like to group it into a new array based on the id field in each subarray.

```php
array
(
    10 => array
          (
            e => array ( id = 10, name = bananas )
          )
    20 => array
          (
            a => array ( id = 20, name = chimpanzee )
            c => array ( id = 20, name = dynasty )
          )
    40 => array
          (
            b => array ( id = 40, name = meeting )
          )
    50 => array
          (
            d => array ( id = 50, name = chocolate )
            f => array ( id = 50, name = fantasy )
            g => array ( id = 50, name = football )
          )
)
```

```php
<?php
$arr = array();
foreach ($old_arr as $key => $item) {
   $arr[$item['id']][$key] = $item;
}
ksort($arr, SORT_NUMERIC);
```

#### 

