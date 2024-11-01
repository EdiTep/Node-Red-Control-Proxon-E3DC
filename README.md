# Proxon T300 Heizung mittles eines ShellyPlus1 MQTT Steuerung mit Node-Red

## Übersicht
Steuerung des PV Vorrang Schalteingangs des T300 Warmwasserspeichers einer Proxon Lüftungsheizung mittles eines ShellyPlus1 über Node-Red und MQTT.
Der ShellyPlus1 wird über Node-Red und MQTT so gesteuert, dass wenn eine bestimmte einstellbare Akkuladung erreicht ist und die Einspeisung eine einstellbare Wattzahl erreicht die Vorrangschaltung aktiviert und bei Unterschreitung der Werte wieder deaktiviert.
Um die Schaltvorgänge mitzubekommen wird bei Aktivierung und Deaktivierung eine Pushover Nachricht verschickt.

X13-1 und X13-2 ist richtig.

Es ist die Platine der T300, auf der auch das Display angelötet ist. Die Platine ist quasi auf der Rückseite des Displays. Dazu muss man zuerst den länglichen Streifen auf der Vorderseite unterhalb des Display herausnehmen. Der ist nur über spitze Krallen seitlich in die Isolierung des Gerätes eingedrückt. Dahinter befinden sich drei Schrauben, die man lösen muss. Dann kann man den gesamten oberen Teil der Geräteisolierung nach oben herausnehmen. Das Display ist in diesen Teil eingeschoben und muss dabei festgehalten werden, damit da nichts kaputt geht.
die Vorrangschaltung der PV Anlage wird am X13 auf der Platine des T300 realisiert. Bitte bedenken, dass es sich hier um einen potentialfreien Kontakt handelt. Es wird also noch ein passendes Relais benötigt. Ich habe dazu einige Infos von der Firma Zimmermann bekommen. Gerne eine Mail per PM hinterlassen und ich kann dir da was zuschicken.

## Installation
1. Node-Red und MQTT Broker installieren.
2. ShellyPlus1 konfigurieren und in das Netzwerk einbinden.

## Node-Red Flow
Hier ist ein Beispiel für den Flow:
```json
{
  "topic": "shelly/command",
  "payload": "on"
}
