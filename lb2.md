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
Mithilfe Vagrant einen Webserver erstellen. Dort wird eine Webseite gehostet. 

## **Grafische Übersicht**
Bild zeigt die Umgebung
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
Linux Grundbefehlen 
| Befehl        | Beschreibung|
| ------------- |:-------------:|
| cd "Ordnername"     | Wechselt in den entsprechenden Ordner    |
| "Befehl" --help     | Zeigt Hilfe für den angegebenen Befehl an     |
| ls     | Inhalt des aktuellen Verzeichnisses anzeigen     |
|mkdir  | Erstellt einen Ordner |
| clear | Terminalausgabe löschen |
| nano "Datei" | Datei bearbeiten  |

### Nginx Service
In den nächsten Zeilen wird beschrieben, wie man einen Nginx Service bereitstellt:

#### Box
Passende Box herauszusuchen. Hier mit: *ubuntu/trusty64*

**Hinweis**: Taste S drucken, damit es ins System bootet!

Mit Befehl die Box initialisieren:

`vagrant init ubuntu/trusty64`

Im lokalen Repository ein Vagrantfile erstellt. Befehl starten:


`vagrant up`

#### Nginx

Verbinden via SSH auf die erstellte Box:

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
| Beschreibung     |  Im Vagrantfile mit Funktion "config.vm.provison" SHELL Befehle durchführen.   |
| Erwartetes Ergebnis     | Der Service Nginx beim vagrant up installieren. |
#### Durchführung
| Tester/in          | Bulliqi Shpat         |
| ------------- |:-------------:|
| Datum     |  18. März 2022  |
| Testergebnis     |  Nginx erfolgreich installiert und gestartet  |
| Fehlerbeschreibung |  Keine  |

#### Testfall 2

| ID            | 02            |
| ------------- |:-------------:|
| Beschreibung     | Static IP Einstellung zu DHCP im Vagrantfile mit Funktion "config.vm.network"   |
| Erwartetes Ergebnis     | Die VM bezieht IP Adresse in meinem Netzwerk über DHCP beim straten |
#### Durchführung
| Tester/in          |  Bulliqi Shpat       |
| ------------- |:-------------:|
| Datum     |  18. März 2022  |
| Testergebnis     |   Die VM konnte nicht starten. Konfiguration im Vagrantfile aus Kommentieren   |
| Fehlerbeschreibung |  "VM cant start a fatal error occured while the network configuration"      |

#### Testfall 3

| ID            | 03            |
| ------------- |:-------------:|
| Beschreibung     | Im Vagrantfile Box Settings apassen mit Funktion "config.vm.provider"     |
| Erwartetes Ergebnis     | CPU und RAM im Vagrantfile angeben. CPU = 2 und RAM = 2 |
#### Durchführung
| Tester/in          |  Bulliqi Shpat        |
| ------------- |:-------------:|
| Datum     | 18. März 2022   |
| Testergebnis     |  Anpassung erfolgreich durchführt      |
| Fehlerbeschreibung |  Keine Fehler  |

### **Reflexion**

Anfangs war ich komplett verloren und habe nichts verstanden was Herr Berger erzählt. Ich habe durch SL mir alles beigebracht und Zusammenhänge verstanden. Ich sehe jedoch den Nutzen für mich in diesem Projekt nicht wirklich und denke das ich es in Zukunft nicht wirklich brauchen werde. Es ist troztdem spannend und interessiert mir wirklich. Auch möchte ich mich an dieser Stelle bei Herr Bayrak bedanken. Er hat mir vieles beigebracht und geholfen. Ich hoffe die lb3 verläuft ähnlich gut wie die lb2.
