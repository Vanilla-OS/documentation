---
title: Menedżer pakietów (apx) - Vanilla OS
description: Dowiedz się, jak korzystać z apx, menedżera pakietów w Vanilla OS
---

# Menedżer pakietów (`apx`)

`apx` jest menedżerem pakietów Vanilla OS. Ma być łatwy w użyciu, ale także 
potężny z obsługą instalacji pakietów z wielu źródeł bez zmiany głównego 
systemu plików.

## Jak to działa

`apx` wprowadza zupełnie nowy paradygmat w zarządzaniu pakietami. Idea polega 
na używaniu systemu tylko jako pudełka do przechowywania plików, pozostawiając 
go czystym od pakietów i ograniczając ryzyko uszkodzenia z powodu niekompatybilnych, 
źle skonstruowanych lub konfliktujących pakietów.

Odbywa się to poprzez instalację oprogramowania wewnątrz jednego lub większej 
ilości "zarządzanych" kontenerów, które są w pełni zarządzane przez `apx` i mają 
ograniczony dostęp do zasobów systemu, podczas gdy nadal mogą korzystać z 
tych samych sterowników, serwera wyświetlania, itp.

Twój katalog domowy jest mapowany wewnątrz kontenera, więc masz dostęp do 
swoich plików konfiguracyjnych, preferencji i innych ważnych danych potrzebnych 
zainstalowanym pakietom, jak również możesz mieć dostęp do własnych plików z 
zainstalowanego oprogramowania, np. otwierając plik w LibreOffice.

### System hosta

Podczas gdy instalowanie oprogramowania na hoście jest sprzeczne z ideologią 
projektu, istnieją przypadki, w których nie można tego uniknąć, na przykład 
gdy trzeba zainstalować moduł jądra.

W takich przypadkach można użyć flagi `--sys` aby ominąć kontener i zainstalować 
bezpośrednio na hoście, *ale pamiętaj, że nie jest to zalecane*. `apx` działa 
z [`almost`](/almost) by tymczasowo wyłączyć niezmienność, pozwalając na 
zainstalowanie potrzebnych pakietów i późniejsze przywrócenie systemu.

### Wiele źródeł

Domyślnie, `apx` zapewnia kontener oparty na Twojej dystrybucji Linuksa (Ubuntu 
22.10 dla Vanilla OS 22.10) i opakowuje wszystkie polecenia z menedżera pakietów 
dystrybucji (`apt` dla Ubuntu).

Niemniej jednak nadal można zainstalować pakiety z innych dystrybucji używając 
innych menedżerów pakietów, na przykład używając flagi `--aur`, zostanie utworzony 
drugi kontener oparty na Arch Linux. Tutaj `apx` będzie zarządzał oprogramowaniem 
z AUR (i Pacmana), zawsze integrując je z systemem hosta.

Dla potrzeb kontroli jakości i testowania, zdecydowaliśmy się ograniczyć tę funkcję 
do konkretnych implementacji. Obecnie obsługiwana jest tylko flaga `--aur`, ale 
planujemy zaimplementować także wsparcie dla menedżera pakietów Nix.

### Nazwa

Nazwa `apx` pochodzi od **apt (Advanced Packaging Tool)**, menedżera pakietów 
używanego przez Debiana i jego pochodne, oraz **X**, który powinien być postrzegany 
jako 2 linie (hosta i kontenera) nakładające się na siebie, gdzie kontener jest na 
górze, co oznacza, że jest na wierzchu systemu hosta.

## Użytek

- [Manpage](/apx/manpage)
