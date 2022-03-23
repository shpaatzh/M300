# LB2 Bulliqi Shpat

----------------------------------------------------------

## **Inhaltsverzeichnis**
* Einleitung
* Grafische Übersicht
* Befehle
    * Vagrant
    * Linux
    * Git
* Nginx Service
* Testfälle
* Reflexion

## **Einleitung**
Für meine LB2 erstelle ich mithilfe von Vagrant einen Webserver. Dort wird eine Webseite gehostet. 

## **Grafische Übersicht**
Das folgende Bild zeigt auf wie die Umgebung aufgebaut ist. 
![Netzwerkplan](Netzwerkplan.png)

## **Befehle**
### **Git**
Lokales Repository erstellen:
```
cd <Name Verzeichnis>
git init
```
Lokales Repository klonen:
```
git clone <Servername>:<Pfad zum Repository> [Verzeichnis-Name]
```
Dateien oder ganze Verzeichnisse unter Git-Verwaltung stellen:
```
git add <Datei-/Verzeichnisname>
```
Aktuellen Projektstand sichern:
```
git commit
```
Repository-Status abfragen:
```
git status
```
Datei verschieben
```
git mv <Quelldatei> <Ziel>
```
Datei löschen
```
git rm <Datei> 
git rm -r <Verzeichnis>
```
Lokalen Arbeitsstand in das entfernte Repository einpflegen
```
git push
```
Aktuellen Dateiinhalt mit dem Stand des letzten Commits vergleichen:
```
git diff <Datei>
```
Versionsgeschichte betrachten
```
git log
```
### **Vagrant** 
Startet VM
```
vagrant up
```
VM herunterfahren
```
vagrant halt
```
Zustand der VM
```
vagrant status
```
SSH Zugriff auf VM
```
vagrant ssh
```
Neustart der VM
```
vagrant reload
```
VM erstellen
```
vagrant init ubuntu/trusty64
```
Netzwerk konfiguration der VM
```
config.vm.network "forwarded_port" 
config.vm.network "private_network"
config.vm.network "public_network"
```

### **Linux** 
Hier ist eine Tabelle mit ein paar Linux Grundbefehlen 
| Befehl        | Beschreibung|
| ------------- |:-------------:|
| cd "Ordnername"     | Wechselt in den entsprechenden Ordner    |
| "Befehl" --help     | Zeigt Hilfe für den angegebenen Befehl an     |
| ls     | Zeigt den Inhalt des aktuellen Verzeichnisses an     |
|mkdir  | Erstellt einen Ordner |
| clear | Terminalausgabe löschen |
| nano "Datei" | Datei bearbeiten (ggf. erstellen) |

### Nginx Service
In den nächsten Zeilen wird beschrieben, wie man einen Nginx Service bereitstellt:

#### Box
Der erste Schritt liegt darin, eine passende Box herauszusuchen. In meinem Fall war es folgende: *ubuntu/trusty64*

**Hinweis**: Taste S drucken, damit es ins System bootet!

Nachdem kann man mit folgendem Befehl die Box initialisieren:

`vagrant init ubuntu/trusty64`

Daraufhin wir im lokalen Repository eon Vagrantfile erstellt. Dies kann man danach mit folgendem Befehl starten:


`vagrant up`

#### Nginx

Um die Webseite zum Nginx Service anzurichten, muss folgenes getan werden:
Als erstes verbindet man sich via SSH auf die eben erstellte Box:

`vagrant SSH`

Nun befindet man sich in einem Linux-Terminal und kann folgende Befehle nacheinander eingeben:

`apt-get update
apt install -y nginx 
service nginx start
service nginx status`



### **Testfälle**
#### Testfall 1

| ID            | 01            |
| ------------- |:-------------:|
| Beschreibung     |  Im Vagrantfile mit folgender Funktion "config.vm.provison" SHELL Befehle durchführen.   |
| Erwartetes Ergebnis     | Der Service Nginx beim vagrant up installieren. |
#### Durchführung
| Tester/in          | Bulliqi Shpat         |
| ------------- |:-------------:|
| Datum     |  18. März 2022  |
| Testergebnis     |  Der Service Nginx wurde erfolgreich installiert und gestartet  |
| Fehlerbeschreibung |  Keine  |

#### Testfall 2

| ID            | 02            |
| ------------- |:-------------:|
| Beschreibung     |  Die Static IP Einstellung zu DHCP ändern im Vagrantfile mit der Funktion "config.vm.network"   |
| Erwartetes Ergebnis     | Die VM bezieht eine IP Adresse in meinem Netzwerk über DHCP beim straten |
#### Durchführung
| Tester/in          |  Bulliqi Shpat       |
| ------------- |:-------------:|
| Datum     |  18. März 2022  |
| Testergebnis     |   Die VM konnte man nicht mehr starten. Ich musste die Konfiguration die ich im Vagrantfile getätigt habe aus Kommentieren   |
| Fehlerbeschreibung |  "VM cant start a fatal error occured while the network configuration"      |

#### Testfall 3

| ID            | 03            |
| ------------- |:-------------:|
| Beschreibung     | Im Vagrantfile die Box Settings apassen mit der funktion "config.vm.provider"     |
| Erwartetes Ergebnis     | Die CPU und die RAM im Vagrantfile angeben. CPU = 2 und RAM = 2 |
#### Durchführung
| Tester/in          |  Bulliqi Shpat        |
| ------------- |:-------------:|
| Datum     | 18. März 2022   |
| Testergebnis     |  Ich konnte erfolgreich die Anpassung durchführen      |
| Fehlerbeschreibung |  Keine Fehler  |

### **Reflexion**

In diesem Projekt, dass ich mehrere Wochen bearbeitet habe, habe ich eine ganz neue Welt entdeckt. Mit Git, Vagrant und Markdown bin ich zuvor noch nie in Berührung gekommen, doch durch dieses Projekt schon. Ich habe sehr viele verschiedene Sachen gelernt, vorallem den Umgang mit Vagrant-, Git- und Markdowncommands habe ich näher kennengelernt. Durch die Partnerarbeit mit Arda, konnte ich das Thema vertiefen, was mir in Zukunft sicher zu Gute kommen wird. Probleme gab es am Anfang, da ich keinen Durchblick und keine Ahnung hatte, wo ich überhaupt Anfangen soll. Je mehr ich mit Git gespielt habe, desto besser habe ich das Ganze verstanden, somit ich schlussendlich dann das Projekt fertig geschafft habe. 
