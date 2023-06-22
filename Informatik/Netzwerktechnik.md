# Netzwerktechnik
von André Sommer am 30.11.2021

## Netzformen
- Bus
- Stern
- Ring
- Baum
- Vermascht

## Ausdehnung von Netzen

|Name|Beschreibung|Ausdehnung|
|---|---|---|
|GAN (Global Area Network)|Wird als globales Netz mit erdumgreifender Dimension verwendet.|>10.000km|
|WAN (Wide Area Network)|Wird als Weitverkehrsnetz, welches ganze Länder umspannt verwendet.|>1.000km|
|MAN (Metropolitan Area Network)|Wird als regionales Netz zum verbinden von LANs verwendet.|100km (WMAN ~50km)|
|SAN (Storage Area Network)|Wird für große Massenspeichernetzwerke (Server für Speicherungen) verwendet.|~10km|
|LAN (Local Area Network)|Verbindet Geräte in Unternehmen, beschränkt sich auf das entsprechende Gelände.|~3km (WLAN ~250m)|
|PAN (Personal Area Network)|Wird für lokale private Netze verwendet (Heimnetz).|~100m|
|CAN (Controller Area Network)|Ursprünglich Car Area Network, wird generell zum vernetzen von Steuerungssystemen verwendet|~500m|
|BAN (Body Area Network)|Wird für medizinische Telemetrie mit Messung am menschlichem Körper verwendet.|~1m|

## Klassifikation nach Übertragungsmodus

### Simplex
Die Kommunikation kann nur unidirektional erfolgen, also nur in eine Richtung.

### Halbduplex
Die Kommunikation ist zwar bidirektional, allerdings nur seriell. Das heißt die Kommunikation kann in beide Richtungen erfolgen, kann Daten aber nur nacheinander und nicht gleichzeitig versenden beziehungsweise empfangen.

### (Full-)Duplex
Bei einem Fullduplex können die Daten sowohl bidirektional als auch parallel versendet werden. Das bedeutet, dass ein Empfänger selbst senden kann, ohne auf eine Antwort warten zu müssen.

|Art|Bidirektional|Parallel|
|---|---|---|
|Simplex|Nein||
|Halbduplex|Ja|Nein|
|(Full-)Duplex|Ja|Ja|

## Klassifikation nach Kommunikationsmuster

### Point to Point
Ein Punkt kann nur an dem nächsten Punkt senden, der kann die Informationen wiederum weiter geben.

### Broadcast
Ein Punkt kann an alle weiteren Punkte senden, muss aber an alle senden und kann nicht differenzieren.

### Multicast
Ein Punkt kann an bestimmte Punkte senden, kann also zwischen Empfängeren differenzieren.

## OSI-Modell 
Please Do Not Throw Salami Pizza Away

|Englische Bezeichnung|Deutsche Bezeichnung|Werkzeuge|Beispiel|
|---|---|---|---|
|Application Layer|Anwendungsschicht|FTP, HTTP, HTTPS, SNMP, SSH, TELNET|Firewall, Anwendung|
|Presentation Layer|Darstellungsschicht|||
|Session Layer|Sitzungsschicht|||
|Transport Layer|Vermittlungsschicht|TCP, UDP|Firewall|
|Network Layer|Netzwerkschicht|IP|Router, Firewall|
|Data Link Layer|Sicherungsschicht|MAC-Adresse|Switch, Netzwerkkarte, Firewall|
|Physical Layer|Bitübertragungsschicht|Mediumsabhängige Kommunikation|Hub, Repeater|

In der TCP/IP Schichtenarchitektur werden die Schichten `Presentation Layer` und `Session Layer` ignoriert und die Schichten `Data Link Layer` und `Physikal Layer` zum `Host-to-Net Layer` zusammengefasst.

|Englische Bezeichnung|
|---|
|Application Layer|
|Transport Layer|
|Network Layer|
|Host-to-Net Layer|

## Kapselung

|Frame (Ramen)|Packets (Pakete)|Segments (Segmente)|Messages (Nachrichten)||
|---|---|---|---|---|
|Header Netzwerkschicht|Header Internetschicht|Header Transportschicht|Daten der Anwendungsschicht|Trailer|
