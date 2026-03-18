# Projekt: Docker-Web-Applikation (Spielfeld-Versionierung)

Dieses Repository enthält die Quellcodedateien und die Konfiguration für eine containerisierte JavaScript-Web-Applikation. Der Schwerpunkt liegt auf der Demonstration eines kontrollierten Image-Build-Prozesses und der Versionierung mittels Docker-Tags.

## Projektübersicht

Ziel des Projekts ist die schrittweise Anpassung einer Spiel-Komponente (Block) und deren Bereitstellung als eigenständige Docker-Images. Jede Aufgabe aus dem Aufgabenkatalog wird durch einen spezifischen Tag im Build-Prozess repräsentiert.

## Dokumentation der Versionen (Tags)

| Version | Aufgabe | Technische Änderung |
| :--- | :--- | :--- |
| **1.0** | Initial | Basis-Image auf Port 80, Standardeinstellungen (Farbe: Blau, Größe: 30x30). |
| **1.1** | Farbe | Änderung des CSS/JS-Attributs `color` von Blau auf Rot. |
| **1.2** | Dimensionen | Anpassung der Variablen `width` und `height` in der Komponenten-Erstellung. |
| **2.0** | Logik-Fix | Implementierung einer Kollisionsabfrage für den oberen Spielfeldrand in der Funktion `hitBottom`. |

## Technische Umsetzung

### Infrastruktur
* **Basis-Image:** Ubuntu 16.04
* **Webserver:** Nginx
* **Laufzeitumgebung:** Docker Engine auf AWS EC2 Instanz

### Build-Prozess
Um eine spezifische Version aus diesem Repository zu bauen, wird der folgende Befehl verwendet:

```bash
docker image build -t game:[VERSION_TAG] .
