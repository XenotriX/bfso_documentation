# Clean Code - Level 1

## Namensgebung \(PHP psr4\)

{% hint style="danger" %}
Die folgenden Informationen beziehen sich auf PHP - andere Programmiersprachen haben andere Regeln. Wichtig ist aber, dass die offiziellen Regeln der Sprache bzw. des Frameworks strikt eingehalten werden!
{% endhint %}

#### Funktionen sollten `lowerCamelCase` verwenden:

`getItemById($id)` Jede Funktion sollte mindestens ein Verb enthalten. `isBirthDay`,`reloadTableData`

#### **Klassen und Interfaces werden gross geschrieben**

`Robot`,`RobotInterface`

#### **Keys werden klein und mit Underscore geschrieben**

`$person['mobile_number'];`

#### **Klarheit ist wichtiger als Kürze**

Besser `getAbsoluteDifference()` als `getAbsDiff()` oder `icrement()` ist besser als `inc()`. Die Abkürzung könnte `include()` oder `increment()` heissen.

#### **Vermeide Lückenfüller wie `item` oder `element` oder `array`**

`foreach ($items as $item)` ist nicht aussagekräftig, besser wäre `foreach($products as $product)`

#### **Übertreibe es nicht mit aussagekräftigen Namen**

`icrease($amount)` ist genauso aussagekräftig wie `increaseByAmount($amount)`

#### **Versuche möglichst so zu programmieren dass es wie eine natürliche Sprache lesbar ist**

`$clients->where('name','is','Frank')->orderBy('name')->get();`

SQL ist ein typisches Beispiel.

`INSERT INTO products (id,name) VALUES (1, 'Sneaker');`

#### **Test Code hat im Programm nichts verloren**

`echo 'Wert von bla ist'.$bla`

{% hint style="danger" %}
#### **Code, Datenbankfelder, Git-Commits und Kommentare sind absolut immer in Englisch zu Schreiben!**
{% endhint %}

## Variablen

#### Schlecht

```php
$d;
```

#### Gut

```php
$daysUntilSaleStart;
```

#### Ausnahme

* Numerische Counter

```php
$i=0;
while($i<100){
    $i++;
}
```

{% hint style="warning" %}
Verwende jede Variable nur für einen Zweck. Kein Variablen-Recycling!
{% endhint %}

## Nutze `return` um Code zu vereinfachen

#### Gut

```php
public function isHidden(){
    if($this->isPublishDateInTheFuture()){
        return true;
    }else{
        return false;
    }
}
```

#### Besser

```php
public function isHidden(){
    if($this->isPublishDateInTheFuture()){
        return true;
    }
    return false;
}
```

## Nutze `continue` und `break` um Code zu vereinfachen

#### Schlecht

```php
foreach($products as $product){
    $abort = false;
    if($product->isSomethingTrue()){
        $abort = true;
    }
    if($product->isSomethingElseTrue()){
        $abort = true,
    }
    if($abort === false){
        $results[] = $product->getResult();
    }
}
```

#### Besser

```php
foreach($products as $product){
    if($product->isSomethingTrue()){
        continue;
    }
    if($product->isSomethingElseTrue()){
        continue;
    }
    $results[] = $product->getResult();
}
```

## Vermeide Verschachtelungen

#### Gut

```php
if(!$product->isHidden()){
    if($product->stock >= $product->mininalStock){
        return $product;
    }else{
        return false;
    }
}
return false;
```

#### Besser

* Code ist besser lesbar
* Fehler werden vermieden
* Code wird generell kürzer

```php
if($product->isHidden()){
   return false; 
}
if($product->stock <= $product->mininalStock){
    return false;
}
return $product;
```

{% hint style="success" %}
Kontrolliere zuerst Spezialfälle - dann der gewünschte oder standardmässige Fall
{% endhint %}

## Umso weniger Parameter umso besser

* Eigene Klassen zu erstellen lohnt sich oft
* Drei Parameter sind aber voll OK

#### Gut

```php
<?php

function createMenu($title, $body, $buttonText, $cancellable) {
    // ...
}
```

#### Besser

```php
$menuConfig = [
    'title' = "Foo",
    'body' = "Bar",
    'button-text' = "Baz",
    "cancellable" = false
];

function createMenu($menuConfig) {
    // ...
}
```

#### Noch Besser

```php
<?php

class MenuConfig
{
    public $title;
    public $body;
    public $buttonText;
    public $cancellable = false;
}

$config = new MenuConfig();
$config->title = 'Foo';
$config->body = 'Bar';
$config->buttonText = 'Baz';
$config->cancellable = true;

function createMenu(MenuConfig $config) {
    // ...
}
```

### 

