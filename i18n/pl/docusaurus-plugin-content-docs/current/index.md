---
title: Dokumentacja Vanilla OS
description: Dowiedz się, jak korzystać z Vanilla OS i wszystkich jego narzędzi oraz ustawień.
sidebar_position: 1
---

# Vanilla OS

Doświadcz czystego GNOME na Ubuntu ze szczyptą charakteru.

## FAQ

Odpowiedzi na najczęściej zadawane pytania (chociaż projekt wciąż jest bardzo młody).
- **Dlaczego nowa dystrybucja?**<br />
  Vanilla OS powstało z potrzeby stworzenia dystrybucji Linuksa opartej na Ubuntu, 
  która dostarczałaby czyste GNOME bez żadnych zmian w końcowym doświadczeniu 
  użytkownika (user experience). Później jego zakres został rozszerzony, aby 
  poeksperymentować z niektórymi narzędziami i technologiami, takimi jak Almost 
  (niezmienność na żądanie) i Apx (podsystem oparty na Distroboxie).
- **Czy wykorzystuje ona OSTree?**<br />
  Nie. Vanilla OS osiąga niezmienność poprzez [`almost`](https://github.com/Vanilla-OS/almost). 
  Napisaliśmy to narzędzie z myślą o niezmienności na żądanie opartej na atrybucie 
  "immutability" plików. To podejście działa na każdym schemacie partycji/systemie plików. 
  Wsparcie dla OSTree może zostać dodane jeszcze w przyszłości.
- **Czy rozwijana jest na bazie modelu "rolling release"?**<br />
  Nie. Vanilla OS posiada tradycyjny model wydawania aktualizacji i podąża za 
  modelem aktualizacji używanym w Ubuntu.

## Sekcje

- **[Niezmienność (`almost`)](/almost)**<br />
Almost to narzędzie dla niezmienności na życzenie oparte na atrybucie "immutability" plików. 

- **[Menedżer pakietów (`apx`)](/apx/)**<br />
Apx jest menedżerem pakietów, który pozwala na instalację i zarządzanie pakietami 
w zarządzanym kontenerze, bez wpływu na system hosta. Czasami możliwe jest użycie 
`apx` do instalacji pakietów również na systemie hosta.
