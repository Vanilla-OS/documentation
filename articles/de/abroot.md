---
Title: Unveränderlichkeit (ABRoot) - Vanilla OS
Description: Erfahren Sie, wie man ABRoot benutzt.
Authors: 
  - Contributors of Vanilla OS
---

`abroot` ist ein Programm, das komplette Unveränderlichkeit und Atomarität bietet, indem es Transaktionen zwischen 2 Root-Partitionen (A⟺B) ausführt. Es ermöglicht auch sofortige Transaktionen mithilfe einer interaktiven Shell.

## Funktionsweise

Das Linux-Dateisystem ist eine hierarchische Struktur, die aus Root und anderen Verzeichnissen besteht.
Root ist das primäre hierarchische Verzeichnis, das alle anderen Partitionen enthält.
In einem unveränderlichen Dateisystem ist die Root-partition schreibgeschützt, was die Installation von grundlegenden Paketen wie Treibern verhindert.

`abroot` ermöglicht die Installation von Kernelmodulen, Treibern und anderen grundlegenden Paketen, ohne die Unveränderlichkeit des Dateisystems zu beeinträchtigen.

Wenn ein Befehl in `abroot` ausgeführt wird, wird eine Transaktion in einer interaktiven Shell in der zweiten Root-Partition ausgeführt. Gelingt die Transaktion, werden die Änderungen mithilfe eines Overlays angewandt und beim Neustart mit der derzeitigen Root-Partition synchonisiert. Scheitert die Transaktion, werden keine Änderungen angewandt (aufgrund einer Eigenschaft namens Atomarität). `abroot` ermöglicht auch sofortige Transaktionen mit dem `abroot shell`-Befehl.

Bei der Installation von Vanilla OS werden Root- und Boot-Partitionen für beide Stadien erstellt (20GB pro Root-Partition), da dies eine Voraussetzung für `abroot` ist.

## Stadien

`abroot` hat zwei Stadien - Gegenwart und Zukunft. Wenn Sie zum ersten Mal Vanilla OS benutzen, ist der gegenwärtige Zustand A. Wird das System neugestartet, wechselt der Zustand automatisch zu B. Wenn ein Paket mit `abroot` installiert wird, wird es in der zukünftigen Root-Partition installiert und beim nächsten Neustart mit der gegenwärtigen Root-Partition synchronisiert.

## Aktualisierungen

`abroot` ist die Basis des `vso`-Programms. Es ermöglicht intelligente, automatische Aktualisierungen und Hintergrundaktualisierungen in der zukünftigen Root-Partition. Dies spart Zeit, da Aktualisierungen nicht beim Neustart eingespielt werden müssen.

## Namensgebung

Der Name ABRoot beschreibt die zwei interagierenden Root-Partitionen A und B (A⟺B).

## Verwendung

- [Manpage](abroot-manpage)
