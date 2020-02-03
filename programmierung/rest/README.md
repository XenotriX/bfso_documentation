# REST

## Verwende korrekte HTTP Methoden:

* GET - Abfrage 
* POST - ~Erstellen/Abfragen 
* DELETE - Löschen 
* PATCH - ~Daten Updaten 
* PUT - ~Daten ersetzen

## Endpoint Beispiele:

{% api-method method="get" host="" path="/v1/products/" %}
{% api-method-summary %}
products
{% endapi-method-summary %}

{% api-method-description %}
Returns all available Products
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "meta": {
    "count": 22,
    "limit": 10,
    "page": 2,
    "previous_url": "/shop/products/?page=1&limit=10",
    "next_url": "/shop/products/?page=3&limit=10"
  },
  "products": [
    {
      "name": "Pineapples",
      "product_url": "/shop/products/33"
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="/v1/products/" %}
{% api-method-summary %}
products
{% endapi-method-summary %}

{% api-method-description %}
Creates a new Product
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="" path="/v1/products/{id}" %}
{% api-method-summary %}
products
{% endapi-method-summary %}

{% api-method-description %}
Updates a given product
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Regeln

#### Verwende die API Version in der URL

`api.cheese.ch/v1/products/`

#### Verwende immer die Mehrzahl

~~/product/{id}~~ 

~~/products/~~

`/products/`

`/products/{id}`

#### Verwende keine Verben!

~~`POST: /products/createNewProduct`~~

`POST: /products/`

#### Gib die Fehlermeldung als JSON zurück \(Und nicht als Text\)

```javascript
{
    "error": "Invalid payload",
    "code": 34,
    "detail": {
        "surname": "This field is required"
    }
}
```

#### GET Parameter sind besser als Nesting

Hier weiss man nicht genau ob man Autoren oder Artikel zurück bekommt:

```javascript
Gut:
/authors/12/articles
```

Hier ist klar dass man alle Artikel zurück bekommt welche der Autor mit der ID 12 geschrieben hat:

```javascript
Besser:
/articles/?author_id=12
```

#### Verwende die korrekten HTTP Status-Codes

{% tabs %}
{% tab title="200" %}
**OK**
{% endtab %}

{% tab title="301" %}
**Moved Permanently**
{% endtab %}

{% tab title="400" %}
**Bad Request**

Die Anfrage-Nachricht war fehlerhaft aufgebaut.
{% endtab %}

{% tab title="401" %}
**Unauthorized**
{% endtab %}

{% tab title="403" %}
**Forbidden**
{% endtab %}

{% tab title="404" %}
**Not Found**
{% endtab %}
{% endtabs %}

#### Verlinke die API da wo es Sinn macht mit href

```text
{
  "id": 312,
  "manufacturer": "VW",
  "model": "Golf",
  "seats": 4,
  "drivers": [
   {
    "id": "23",
    "name": "Paul Müller",
    "links": [
     {
     "rel": "self",
     "href": "/api/v1/drivers/23"
    }
   ]
  }
 ]
}
```

#### Filter und Sortierung ermöglichen

```text
GET /cars?color=red //Returns a list of red cars
```

#### Auswahl der Felder erlauben

So kann der Payload minimiert werden

```text
GET /cars?fields=manufacturer,model,id,color
```

## Fragen welche man sich stellen kann

* Wie viele Daten werden Synchronisiert? 100 oder 100 000?
* Wird direkt auf die Daten zugegriffen? Oder werden die Daten zwischengespeichert?

## Sicherheit

z.B. OAuth oder BasicAuth

## Dokumentation

Am Besten vor der Implementation

## Bibliotheken

#### C\#

{% embed url="http://restsharp.org/getting-started/\#asynchronous-calls" %}

#### PHP

{% embed url="http://docs.guzzlephp.org/en/stable/" %}

## Schnittstelle Testen mit Postman

{% embed url="https://www.getpostman.com/" %}

## Videos

{% embed url="https://www.youtube.com/watch?v=aWePkE2ReGw" %}



## Andere Schnittstellen

{% embed url="https://blog.apollographql.com/graphql-vs-rest-5d425123e34b" %}

{% embed url="https://www.computerweekly.com/de/tipp/REST-versus-SOAP-Den-passenden-Webservice-auswaehlen" %}







