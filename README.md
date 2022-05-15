## Yacht
*Shpat Bulliqi*

# Was ist Yacht?
    Yacht ist eine schlanke Verwaltungsoberfläche, mit der Sie Ihre verschiedenen Docker-Container einfach verwalten können.

    Yacht bietet eine leichte und einfache Lösung für die Verwaltung von Docker-Containern über eine Weboberfläche. \
    Yacht unterstützt eine breite Palette von Funktionen für die Verwaltung von Docker-Containern, wie z. B. die Verwaltung oder der Erstellung von Applikationen.

Aus dem englischen Übersetzt, Quelle: [Yacht: Documentation](https://yacht.sh/docs/)

# Inhaltsverzeichnis
- **[Umgebung](#Umgebung)**
  - [VM-Spezifikationen](#vm-spezifikationen)
- **[Sourcecode](#Sourcecode)**
  - [Docker-Compse File](#docker-compse-file)
  - [Basis Konfiguration](#basis-konfiguration)
    - [Yacht Docker-Container](#yacht-docker-container)
    - [Abschluss](#abschluss)
- **[Fazit](#Fazit)**
- **[Testing](#Testing)**
- **[Quellen](#Quellen)**

  
## VM-Spezifikationen:

| **Attribut** | **Wert** |
-------|---------------
| IPv4 | 192.169.4.50 |
| CPU-Cores | 5 |
| Memory | 8GB |
| USB | off |
| USBehci | off |

# Sourcecode

## Docker-Compse File

```ruby
version: "3"
services: 
  yacht:
    container_name: yacht
    restart: unless-stopped
    ports:
      - 8000:8000
    volumes:
      - yacht:/config
      - //var/run/docker.sock:/var/run/docker.sock
    image: selfhostedpro/yacht

volumes:
  yacht:
end
```

## Basis Konfiguration

Zu Begin wird im Vagrantfile die grundsätzlichen Informationen, \
wie zum Beispiel Port und Image.

### Yacht Docker-Container
Vor dem Starten des Cotainers, wird ein [Dockervolume](https://yacht.sh/docs/Installation/Install) erstellt, \
wo später die Dateien des containers abgelegt werden, sodass diese beim stoppen des Containers nicht verloren gehen. \
Nun wird das [Yacht](https://yacht.sh/docs/Installation/Install) Dockercontainerimage gestartet. \
Folgende [Docker run Container-Parameter](https://yacht.sh/docs/Installation/Install) wurden verwendet: \
| Parameter | Beschreibung |
------------|---------------
| `-d` | **_"detached"_** macht, dass der Container im Hintergrund läuft und nicht z.B. Ausgaben ins Linux-terminal schreibt |
| `-p` | **_"port"_** mit diesem Parameter können Container Ports an Host-Ports gebunden werden |
| `--name` | der name des Containers |
| `-v` | **_"volume"_** hier wird angegeben welcher Container-Pfad an welchen Host-Pfad gebunden wird |

# Fazit
Sobald das Vagrantfile, mit `vagrant up` gestartet wird, kann auf das [Yacht WebGUI](http://localhost:8000/#/) zugegriffen werden.

Wenn die Installation erfolgreich war sollte nun eine Site zusehen sein, \
wo beim ersten Login die Admin-Benutzer informationen gesetzt werden müssen, das heisst Passwort und Nutzername (Benutzername: admin@yacht.local Passwort: pass).

# Testing
Ein simpler Anmeldetest aoll durchgeführt werden.

![Anmeldung](C:\Users\Shpat\Downloads) 

# Quellen
[Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

[Vagrant Website](https://www.vagrantup.com/)

[Yacht Website](https://yacht.sh/docs//)