# Clean Code - Level 2

## Kommentare

#### Schlecht

```php
// This function runs a single check 
public function run($course, $checkname){

}
```

#### Besser

* Kommentare nur falls sich die Information nicht in `Methoden` oder `Variablennamen` unterbringen lassen.
* Kommentare brauchen Wartung
  * Falsche Kommentare sind irreführend

```php
public function runSingleCheck($course, $checkname){

}
```

#### Oft sind aber Kommentare notwendig

```php
/**
 * Get the plugin renderer for a specific check, if it doesn't exist, fallback to the default one.
 *
 * @param string $checkerName plugin name
 * @return GlobalPluginRenderer
 */
public function getRenderer($checkerName) {

}
```

## Boy Scout Rule

{% hint style="info" %}
Jedes Mal wenn du eine Zeile Code änderst, kontrolliere die umgebenden Zeilen und verbessere diese.
{% endhint %}

## Plugins

{% hint style="info" %}
Schreibe ein Plugin möglichst so dass es auch mit anderen Frameworks funktionieren würde
{% endhint %}

## Code Style Guide

#### z.B. für PHP PSR4

```php
function getRenderer()    // camelCase Funktionen
{
    $checkerName;    // camelCase Variabeln
}


function test_get_renderer()
{ // Unit-Tests
    
}

// usw.
```

* Das Team muss sich für Style Guides entscheiden
* Die IDE kann Fehler erkennen

## Namespaces

* Namespaces dienen dazu dass Klassen mit demselben Namen in demselben Projekt möglich sind. Dies ist besonders wichtig wenn man Drittanbieter-Plugins verwendet.

```php
<?php
namespace Laravel\Lumen\Bus;
class PendingDispatch
{
    
}
```

## Naming Conventions

{% hint style="success" %}
In einem Projekt lohnt es sich Namensconventionen zu definieren
{% endhint %}

`map-teachers-to-products`ist nicht dasselbe wie `map-products-to-teachers`

Unterschiede zwischen:

```text
link  
unlink
map 
sync
create 
save
update
delete 
destroy
```

