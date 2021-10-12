# KEW - Präsentation: PiHole

Sammlung der Inhalte und Präsentation für das Thema PiHole auf der KEW 2021

## Über die AG Link

Du findest uns hier: https://ag-link.xyz/

## Kompatible Modelle
  - Raspberry Pi Zero W
  - Orange Pi
  - Raspberry Pi 3 B+ (oder höher)

## Pi-Hole Setup
Part 1: Ein Betriebssystem auf dem Pi installieren und eine Verbindung aufbauen.

1. Das Image mit dem Betriebssystem herunterladen (wir verwenden Raspberry OS light).
2. Image auf SD karte schreiben (Zum Beispiel mit `edger` oder `rpi-imager`). Von dieser
  SD Karte wird dann der Raspberry Pi gestartet.
3. Bevor wir die SD Karte in den Pi Stecken und booten konfigurieren wir noch den 
  Zugang zum WLAN, damit wir uns direkt von unserem Computer mit Pi verbinden können
  Hierfür die folgenden Schritte auf der SD Karte durchführen:
  3.1. Unter /boot/ eine Datei mit dem Namen "wpa_supplicant.conf" anlegen. Den 
    Inhalt findest du hier: `link`.
  3.2. Ebenfalls unter /boot/ eine leere Datei mit dem namen "ssh" erstellen (Keine 
    Dateiendung wie .txt). hierfür könnt ihr auf unix systemen mit einfach `touch ssh` 
    ausführen.
4. Die SD Karte in den Pi stecken und an den Strom anschließen. Der Pi booted jetzt.
5. In diesem Schritt verbindest du dich von deinem Computer per SSH (secure shell) 
  mit dem Pi. Hierfür muss sich dein Computer im gleichen WLan befinden. SSH ermöglicht
  dir aus dem Terminal heraus befehle auf deinem PI auszuführen und so Dienste zu starten
  oder Dateien zu lesen/verändern. 
      
    5.1. Um uns per SSH mit dem Pi zu verbinden benötigen wir zuerst dessen IP, also die Adresse
      im lokalen Netzwerk. Auf Unix hilft hier das Tool nmap. In einem Terminal 
      `sudo nmap -sn 192.168.0.1/24` ausführen (-sn steht für scan network) gibt eine Liste aller 
      hosts im Netzwerk zurück. Alternativ könnt ihr euch auch mit eurem Router verbinden und 
      eine Liste aller verbundenen Geräte anzeigen lassen.  
      Ouput könnte zum Beispiel so aussehen:
      > Nmap scan report for pi.hole (192.168.0.11) <br>
      > Host is up (0.10s latency). <br>
      > MAC Address: A1:22:CC:44:D5:6E (Raspberry Pi Foundation)
    
      Uns interessiert hier die IP *192.168.0.11*
  
    5.2. Zeit uns mit dem PI zu verbinden! In einem Terminal auf eurem PC gibst du:
      `ssh pi@<ip-adresse-des-pi>` ein, um die SSH verbindung aufzubauen.
      Bei der frage ob der Fingerprint hinzugefügt werden soll <yes> antworten.
      
    5.3. `raspberry` als Passwort eingeben
    
**Herzlichen Glückwunsch** du hast jetzt ein Betriebssystem auf deinem Pi eingerichtet 
und kannst diesen von deinem Computer aus steuern 
  -> gib `pwd` ein, um dir den Pfad ausgeben zu lassen auf dem du dich mit dem Terminal
  jetzt auf dem Pi befindest.


Part 2: Das System updaten und PiHole installieren
1. Als erstes solltest du dein System updaten. Wie bei allen Linux Distributionen die auf 
  Debian basieren (Ubuntu etc.), updatest du die Packetquellen mit `sudo apt update` und 
  installierst die anschließen die neusten Versionen mit `sudo apt upgrade`.
2. Als nächstes laden wir die Pi-Hole Software herunter und installieren diese.
  **Leider bietet PiHole derzeit keine Installation über die offiziellen Packetquellen an. Bei unbekannten Quellen sollte das pipen von curl nach bash immer vermieden werden.**
  `curl -sSL https://install.pi-hole.net | sudo bash`

In [diesem Artikel](https://medium.com/swlh/how-to-set-up-pi-hole-2293246dc8ed) wird die weitere Konfiguration sehr anschaulich beschrieben.

Ein ausführliche Installationsanleitung ist auch auf der [offiziellen Pi-hole Website zu finden](https://github.com/pi-hole/pi-hole/#one-step-automated-install)



## Quellen

* [IOC Update Report into adtech and Real Time Bidding](assets/rtb/adtech-real-time-bidding-report-201906.pdf)
* [IAB TCF Vendor List](https://iabeurope.eu/vendor-list-tcf-v2-0/)
* [Selling Off Privacy At Auction](assets/rtb/SellingOffPrivacyAtAuction.pdf)

(weitere Quellen finden sich in den Slides der Präsentation)
