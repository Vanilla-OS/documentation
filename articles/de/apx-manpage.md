---
Title: Manpage apx - Vanilla OS
Description: Manpage für das apx-Programm.
Authors: Contributors of Vanilla OS
---

## NAME

```text
`apx` - Der nutzerfreundliche Vanilla OS-Paketverwalter mit Unterstützung für die Installation von Paketen aus verschiedenen Quellen in Containern, um das Root-Dateisystem nicht zu verändern.
```

## ÜBERSICHT

```text
apx [Optionen] [Befehl] [Argumente]
```

## BESCHREIBUNG

```md
apx ist ein Wrapper um mehrere Paketvervaltungprogramme, der Installationen und andere Befehle in einem verwalteten Container durchführt.

Aufruf:
    apx [Optionen] [Befehl] [Argumente]

Optionen:
    -h, --help      Diese Hilfe ausgeben und beenden
    -v, --version   Versionsinformation anzeigen und beenden
    --aur           Pakete aus dem AUR installieren
    --dnf           Pakete aus dem Fedora-Repository installieren

Befehle:
    autoremove      Alle nicht genutzten Pakete entfernen
    clean           Cache des apx-Paketverwalters leeren
    enter           Container-Shell öffnen
    export          Menüeintrag eines Programms aus dem Container exportieren
    help            Diese Hilfe ausgeben und beenden
    init            Einen verwalteten Container initialisieren
    install         Paket innerhalb des Containers installieren
    list            Installierte Pakete auflisten
    log             Logdateien anzeigen
    purge           Pakete und Konfigurationsdateien vom Container entfernen
    run             Befehl innerhalb des Containers ausführen
    remove          Pakete vom Container entfernen
    search          Nach Paketen suchen
    show            Details über ein Paket anzeigen
    unexport        Menüeintrag eines Programms entfernen
    update          Liste der verfügbaren Pakete aktualisieren
    upgrade         Verfügbare Paketaktualisierungen anwenden
    version         Versionsinformation anzeigen und beenden
```

## AUTOREMOVE

```md
Beschreibung: 
    Alle nicht genutzten Pakete automatisch entfernen.

Aufruf:
    apx autoremove [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden

Beispiele:
    apx autoremove
```

## CLEAN

```md
Beschreibung: 
    Cache des apx-Paketverwalters leeren.

Aufruf:
    apx clean [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden

Beispiele:
    apx clean
```

## ENTER

```md
Beschreibung: 
    Die Shell des gegebenen Containers öffnen.

Aufruf:
    apx enter [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden
```

## EXPORT

```md
Beschreibung: 
    Den Menüeintrag eines Programms aus einem verwalteten Container exportieren/neuerstellen.

Aufruf:
    apx export <Programm> [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden

Beispiele:
    apx export htop
```

## INIT

```md
Beschreibung: 
    Einen verwalteten Container initialisieren.

Aufruf:
    apx init [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden
```

## INSTALL

```md
Beschreibung: 
    Pakete innerhalb eines verwalteten Containers installieren.

Aufruf:
    apx install [Optionen] <Pakete>

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden
    -y, --assume-yes      Ohne manuelle Bestätigung fortfahren
    -f, --fix-broken      Vor der Installation beschädigte Abhängigkeiten reparieren
    --no-export           Menüeintrag nach der Installation nicht exportieren
    --sideload [Pfad]     Paket von einer lokalen Datei installieren

Beispiele:
    apx install htop git
    apx install --sideload /Pfad/zur/Datei.deb
```

## LIST

```md
Beschreibung: 
    Installierte Pakete auflisten.

Aufruf:
    apx list [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden
```

## PURGE

```md
Beschreibung: 
    Pakete und Konfigurationsdateien in einem verwalteten Container entfernen.

Aufruf:
    apx purge <Pakete> [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden

Beispiele:
    apx purge htop
```

## REMOVE

```md
Beschreibung:
    Pakete in einem verwalteten Container entfernen.

Aufruf:
    apx remove <Pakete> [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden

Beispiele:
    apx remove htop
```

## RUN

```md
Beschreibung: 
    Programm in einem verwalteten Container ausführen.

Aufruf:
    apx run <Programm> [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden

Beispiele:
    apx run htop
```

## SEARCH

```md
Beschreibung: 
    In einem verwalteten Container nach Paketen suchen.

Aufruf:
    apx search <Pakete> [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden

Beispiele:
    apx search htop
```

## SHOW

```md
Beschreibung: 
    Details über ein Paket anzeigen.

Aufruf:
    apx show <package> [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden

Beispiele:
    apx show htop
```

## UNEXPORT

```md
Beschreibung:
    Menüeintrag eines Programms aus einem verwalteten Container entfernen.

Aufruf:
    apx unexport <Programm> [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden

Beispiele:
    apx unexport htop
```

## UPDATE

```md
Beschreibung: 
    Die Liste der verfügbaren Pakete aktualisieren.

Aufruf:
    apx update [Optionen]

Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden

Beispiele:
    apx update
```

## UPGRADE

```md
Beschreibung: 
    Verfügbare Paketaktualisierungen anwenden.

Aufruf:
    apx upgrade [Optionen]
  
Optionen:
    -h, --help            Diese Hilfe ausgeben und beenden

Beispiele:
    apx upgrade
```

## VERSION

```md
Beschreibung:
    Die apx-Version anzeigen.

Aufruf:
    apx --version
    apx -v
```

## SIEHE AUCH

- [`abroot`](abroot)
- [`vso`](vso)

## AUTHOR

```text
Mitwirkende von Vanilla OS
```

## FEHLER MELDEN

Fehler bitte beim [Bugtracker](https://github.com/Vanilla-OS/apx/issues) melden.
