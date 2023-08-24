---
Title: Paketmanager (apx) - VanillaOS
Description: Bedienungsanleitung des Paketmanagers von VanillaOS, apx
Authors: Contributors of Vanilla OS
---

# Paketmanager (`apx`)

`apx` ist der Paketmanager von VanillaOS. Er macht es möglich Dateien aus verschiedenen Paketquellen zu beziehen, ohne das Root-Dateisystem zu verändern.



## Funktionsweise

Die `apx` zugrunde liegenden Funktionsweisen sind vollkommen neuartige Konzepte der Paketverwaltung. Die Idee ist, dass ihr System nur als Behälter für ihre persönlichen Daten dient, es ist also völlig frei von Paketen. Das verringert das Risiko, dass inkompatible oder beschädige Pakete ihre Daten zerstören. 

Dies wird durch sogenannte Container erreicht. Die Software, die Sie installieren wird in diesen Containern gespeichert. Die Container werden vollautomatisch von `apx` verwaltet. Durch dieses Verstauen der Programme in den Containern haben diese nicht auf alle Teile des Systems Zugriff, was wiederum die Sicherheit erhöht. Auf Dienste wie den Anzeigeserver und die Treiber für die Komponenten des PC haben aber alle Programme Zugriff.

Damit sie Dateien aus ihrem Home-Verzeichnis in Programmen öffnen können, werden werden Konfigurationsdateien und andere Daten, die von den Programmen benötigt werden, innerhalb der Container gespiegelt. 

### Host-System

Das Installieren von Software auf dem Host-System widerspricht der Philosophie des Projekts, ist aber in manchen Fällen unvermeidbar. Zum Beispiel beim Updaten/Installieren von Kernelmodulen.

In solchen Fällen würden Sie das `--sys` Flag verwenden, um den Container zu umgehen und  die Pakete direkt auf dem Host zu installieren, *aber seien Sie sich bewusst, dass dies nicht empfohlen wird*.

`apx` arbeitet mit [`almost`](/docs/almost), um die Unveränderlichkeit vorübergehend zu deaktivieren, 
Dies erlaubt Ihnen, die benötigten Pakete zu installieren und das System anschließend wiederherzustellen.

### Mehrere Quellen

Standardmäßig bietet `apx` einen Container, der auf Ihrer Linux-Distribution basiert (Ubuntu 22.10 für Vanilla OS 22.10) und wickelt alle Befehle aus dem Paketmanager der Distribution Paketmanager der Distribution (`apt` für Ubuntu).

Dennoch ist es möglich Pakete von anderen Distributionen zu installieren. Wenn Sie zum Beispiel bei der Verwendung von `apx` die `--aur` Option angeben wird ein neuer, auf Arch-Linux basierender Container erstellt. Die Software wird dann innerhalb des Containers mit dem Paketmanager von Arch (`pacman`) installiert und in das Host-System integriert.

Aus Gründen der Qualitätssicherung sind nur einige Distributionen unterstützt.

### Der Name

Der Name `apx` kommt von **apt (Advanced Packaging Tool)**, dem Paketmanager, der von Debian und seinen Derivaten verwendet wird. Das **X** besteht aus 2 Zeilen und symbolisiert das Host- und das Container-System, wobei der Container das Host--System überlagert.

## Verwendung

- [Manpage](apx-manpage)
