# Dokumentation

Dieses Devfile dient der Erstellung einer Entwicklungsumgebung mit Eclipse Che. 

## Metadata

Metadaten des Projektes für die Darstellung in Che

**name**: Name des Workspaces in Che

## Projects

Legt die Projekte (oberste Ordner) im IDE selbst fest. Mehrer Einträge möglich.

**name**: Name des Ordners

### Source

Quelle des Projektes

**location**: Link zum Projekt  
**type**: Typ des Projekt-Links `zip` oder `git`  
**branch**: Welche Git-Branch (bei Projekttyp git)  

## Arrtibutes

Sonstiges Attribute für den Container

**persistVolumes**: Legt fest ob Änderungen gespeichert werden sollen oder nicht

## Components

Komponenten des Che-Editors. Hier werden Images angegeben die festlegen welcher Container, welche Plugins & welcher Editor verwendet werden.

**id**: `publisher/name/version` des Plugins aus der Che Plugin Registry  
**type**: `cheEditor`, `chePlugin`, `kubernetes` oder `dockerimage`  
**mountSources**: Ob der Container Zugriff auf die Projekt-Datein haben soll  
**memoryLimit**: RAM-Limit für Docker-Cotainer  
**alias**: Ein einzigartiger Name für diesen Component der verwendet wird um im Devfile auf die Datei zu verweisen  
**image**: Pfad zum Docker-Image

### Volumes
Volumes für Docker-Container  

**name**: Name des Volumes um später auf es zu verweisen  
**containerPath**: Pfad der gemounted werden soll (ähnlich wie bei Docker)  

### Env

Umgebungsvariablen für den Docker-Container

**value**: Wert der Variable
**name**: Name der Variable

## Commands

**name**: Name des Commands

### Actions

Aktionen die von dem Command ausgeführt werden

**workdir**: In welchem Ordner der Command ausgeführt werden soll  
**type**: `exec`  
**component**: Component in dem der Befehl ausgeführt wird  
**command**: Der Befehl selbst  

