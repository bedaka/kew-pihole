# WWW - Eine Einführung

## Über die AG Link

Ein paar Sätze zur AG Link. Vision und bisherige Projekte nennen.

## Wie funktioniert das Web (Basic)

Quellen:
  - [What happens when you type in a
      URL](https://wsvincent.com/what-happens-when-url/)


1. You enter a URL into a web browser
2. The browser looks up the IP address for the domain name via DNS
3. The browser sends a HTTP request to the server
4. The server sends back a HTTP response
5. The browser begins rendering the HTML
6. The browser sends requests for additional objects embedded in HTML and
   repeats steps 3-5
  - images, 
  - CSS
  - JavaScript
7. Once the page is loaded, the browser sends further async requests as needed.


### HTTP

### DNS

### Was läd der Browser wenn ich die New York Times aufrufe?

*Hier könnten man einen Screenshot vom Network-Tab des Browsers einfügen,
nachdem man https://www.nytimes.com aufgerufen hat.*

## Wie funktionieren Ad Blocker?

Definition: Ad Blocker sind Browser Plugins/Extensions, die Ressource im HTML
gegen eine Liste bekannter Werbe- oder Trackdienste abgleichen und das Laden der
jeweiligen Inhalte notfalls blockieren.

Populäre Ad Blocker:
  - UBlock Origin
  - …

## PiHole

Die Vorteile auf einem Blick:
  - Schütze das gesamte Netzwerk auf einmal
  - Blockiere Tracker in Smart TVs und Mobile Apps
  - Erhöhte Netzwerkperformance: Tracker werden geblockt bevor sie herunter
      geladen werden
  - Überblick auf die Gesamtmenge der blockierte Tracker durch PiHole
      Webinterface
