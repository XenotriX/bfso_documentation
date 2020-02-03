# Web Technologien

### HTML

Alle Webseiten sind mit HTML aufgebaut. HTML gibt Webseiten seine Struktur. Was das genau bedeutet, schauen wir uns am Besten mit einem Beispiel an:

#### Beispiel

* Erstelle die Datei `index.html`
* Füge folgendes in die Datei ein:

  ```markup
  <html>
    <head>
    </head>
    <body>
        <h1>Das ist ein Titel</h1>
        <p>Das ist ein Absatz,
        dies ist eine neue Zeile</p>
    </body>
  </html>
  ```

* Speichere die Datei und öffne Sie direkt in deinem Browser des Vertrauens
* Füge ein `<br>` hinter `Absatz,` ein um nach `Absatz,` eine neue Zeile anzufangen

Ganz einfach? Na ja, ganz so einfach ist es nicht. Es gibt über 100 `HTML` Elemente wie zum Beispiel `<H1>`. Damit man Tabellen, Aufzählungen, Bilder und vieles mehr erstellen kann.

**Weitere Informationen**

* [HTML](/docs/{{version}}/webtechnologien/html)
* [HTML-Elemente](/docs/{{version}}/webtechnologien/html-elemente)

### CSS

CSS ist eine Ergänzung HTML. Mit CSS können Farben, Abstände, Schriftgrössen und vieles mehr definiert werden.

Beispiel

* Füge folgendes Snippet \(Codeschnipsel\) zwischen den HTML Tags `<head>` und `</head>`, also dem Kopfbereich deiner Homepage, ein.

  ```markup
  <style>
    h1 {color:green;}
  </style>
  ```

Wir haben den H1 \(Header1\) Titel unserer Homepage grün gefärbt. Yeaaaaahh grün :\)

### JavaScript

Javascript ist das letzte Mitglied im Triumvirat mit HTML und CSS. Javascript ist dafür verantwortlich, dass man einer Homepage Leben einhauchen kann.

* Füge folgendes Script vor dem `</body>` Tag ein

  ```markup
  <button onclick="sayHello()">Drück mich</button>
  <p id="demo"></p>
  <script>
    function sayHello() {
          document.getElementById("demo").innerHTML = "Hello World";
    }
  </script>
  ```

### XML

XML ist ähnlich aufgebaut wie HTML, dient aber zur Speicherung und Strukturierung von Daten. Hier ein Beispiel:

```markup
<?xml version="1.0" encoding="UTF-8"?>
<note>
    <to>Tove</to>
    <from>Jani</from>
    <heading>Reminder</heading>
    <body>Don't forget me this weekend!</body>
</note>
```

**Wo wird XML verwendet?**

* Google Shopping Feed
* Datenübertragung
* Konfigurationen
* [https://www.ch.ch/sitemap.xml](https://www.ch.ch/sitemap.xml)

