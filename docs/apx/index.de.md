---
Titel: Package Manager (apx) - Vanilla OS
Beschreibt: Wie man apx, den Vanilla OS Paketmanager, benutzt.
---

# Paketmanager (`apx`)
`apx` ist der Vanilla-OS-Paketmanager. Er soll einfach zu benutzen sein, aber 
mit Unterstützung für die Installation von Paketen aus mehreren Quellen ohne 
ohne das Root-Dateisystem zu verändern.

## Wie es funktioniert
`apx` führt ein völlig neues Paradigma in der Paketverwaltung ein. Die Idee ist, das 
Ihr System nur als eine Box für die Speicherung Ihrer Dateien zu verwenden, so dass es frei von Paketen ist 
und das Risiko zu begrenzen, dass es aufgrund von inkompatiblen, schlecht konstruierten oder 
widersprüchliche Pakete.

Dies wird durch die Installation von Software in einem oder mehreren "verwalteten" Containern erreicht, 
die vollständig von `apx` verwaltet werden und eingeschränkten Zugriff auf die Ressourcen Ihres Systems haben 
Ressourcen Ihres Systems haben, aber dennoch dieselben Treiber, Anzeigeserver usw. verwenden können.

Ihr Home-Verzeichnis wird innerhalb des Containers abgebildet, so dass Sie auf Ihre 
Konfigurationsdateien, Einstellungen und andere wichtige Daten, die von den installierten 
Pakete benötigt werden, sowie auf Ihre eigenen Dateien von der installierten Software aus zugreifen können 
Software zugreifen können, z. B. durch Öffnen einer Datei in LibreOffice.

### Host-System
Die Installation von Software auf dem Host-System widerspricht zwar der Ideologie des Projekts, 
gibt es Fälle, in denen dies nicht vermieden werden kann, z.B. wenn Sie 
ein Kernelmodul installieren müssen.

In solchen Fällen würden Sie das `--sys` Flag verwenden, um den Container zu umgehen und 
um den Container zu umgehen und direkt auf dem Host zu installieren, *aber seien Sie sich bewusst, dass dies nicht empfohlen wird*. `apx` 
arbeitet mit [`almost`](/docs/almost), um die Unveränderlichkeit vorübergehend zu deaktivieren, 
Dies erlaubt Ihnen, die benötigten Pakete zu installieren und das System anschließend wiederherzustellen.

### Mehrere Quellen
Standardmäßig bietet `apx` einen Container, der auf Ihrer Linux-Distribution basiert (Ubuntu 
22.10 für Vanilla OS 22.10) und wickelt alle Befehle aus dem Paketmanager der Distribution 
Paketmanager der Distribution (`apt` für Ubuntu).

Dennoch ist es möglich, Pakete von anderen Distributionen zu installieren 
Paketmanager zu installieren, z.B. mit dem `--aur` Flag, wird ein zweiter 
Container auf der Basis von Arch Linux erstellt werden. Hier wird `apx` die Software 
aus dem AUR (und Pacman) verwalten, wobei es immer in das Wirtssystem integriert wird.

Aus Gründen der Qualitätskontrolle und des Testens haben wir uns entschieden, diese Funktion 
auf bestimmte Implementierungen zu beschränken. Derzeit wird nur das `--aur`-Flag unterstützt, aber 
wir planen, auch die Unterstützung für den Nix-Paketmanager zu implementieren.

### Der Name
Der Name `apx` kommt von **apt (Advanced Packaging Tool)**, dem Paketmanager 
Paketmanager, der von Debian und seinen Derivaten verwendet wird, und **X**, was als 
2 Zeilen (Host und Container), die sich überlappen, wobei der Container oben ist, was bedeutet 
dass er über dem Wirtssystem steht.

## Verwendung
- [Manpage](/docs/apx/manpage)
