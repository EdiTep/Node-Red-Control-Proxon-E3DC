# Proxon T300 Warmwasser Speicher PV Vorrang Schalteingangs mit ShellyPlus1 per MQTT und Node-Red steuern

## Übersicht des Projekts
Steuerung des PV Vorrang Schalteingangs des T300 Warmwasserspeichers einer Proxon Lüftungsheizung mittles eines ShellyPlus1 über Node-Red und MQTT.
Der ShellyPlus1 wird über Node-Red und MQTT so gesteuert, dass wenn eine einstellbare Akkuladung und die Einspeisung eine einstellbare Wattzahl erreicht die Vorrangschaltung aktiviert und bei Unterschreitung der Werte wieder deaktiviert wird.
Um die Schaltvorgänge mitzubekommen auch wenn niemand daheim ist wird bei Aktivierung und Deaktivierung eine Pushover Nachricht verschickt.

Auf der Platine des T300, auf der auch das Display angelötet ist gibt es den Klemmblock X13. Die Platine ist auf der Rückseite des Displays. Um an den Klemmblock zu gelangen muss man zuerst den länglichen Streifen auf der Vorderseite unterhalb des Display herausnehmen. Der ist nur über spitze Krallen seitlich in die Isolierung des Gerätes eingedrückt. Dahinter befinden sich drei Schrauben, die man lösen muss. Dann kann man den gesamten oberen Teil der Geräteisolierung nach oben herausnehmen. Das Display ist hier in zwei Nuten eingeschoben und muss beim herauschieben festgehalten werden, damit kein Defekt entsteht.
Die Vorrangschaltung der PV Anlage befindet sich am Klemmblock X13 an X13-1 und X13-2 wird der Schalteingang des ShellyPlus1 angeschlossen. Bitte bedenken, dass es sich hier um einen potentialfreien Kontakt handelt. Das passendes Relais ist in dem Fall der ShellyPlus1. Nachdem ich bei der Firma Zimmermann angefaragt habe, haben sie mir eine CVS Datei geschickt, auf der alles Modbus Infos ersichtlich sind, die Beschaltung ist auf den Schaltplänen ersichtlich, die mir bei der Abnahme überlassen wurden. Gerne eine Mail per PM hinterlassen und ich kann dir die CSV Daei zuschicken.

## Installation, Voraussetzungen
1. Raspberry Pi als Host für die weiteren Voraussetzungen
2. Node-Red mit Dashboard und MQTT Broker installieren
3. RSCP to MQTT Dashboard v1.0
   https://github.com/pvtom/rscp2mqtt-dashboard
4. ShellyPlus1 konfigurieren und in das Netzwerk einbinden

## Node-Red Flow
Der Flow ist als JSON Datei im Projekt und kann herunter geladen werden oder der JSON Code kopiert werden

