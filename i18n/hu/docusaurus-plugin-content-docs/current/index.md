---
title: Vanilla OS leírás
description: A Vanilla OS használata az eszközeivel és beállításaival.
sidebar_position: 1
---

# Vanilla OS

Kóstolja meg a Vanilla GNOME élményt Ubuntu-n enyhén fűszerezve. 

## GYIK

Válaszok a leggyakrabban ismételt kérdésekre (pedig a projekt elég fiatal).
- **Miért egy új disztribúció?**<br />
  A Vanilla OS egy olyan Ubuntu alapú Linux disztribúció hiányában jött létre, 
  amely vanilla GNOME-ot kínál, a felhasználói élmény módosítása nélkül. 
  Később, az elképzelés ki lett terjesztve pár eszközzel és technológiával, mint 
  az Almost (igény szerinti felülírhatatlanság) és az Apx (a Distrobox alapú 
  alrendszer).
- **OSTree-t használ?**<br />
  Nem. A Vanilla OS az [`almost`](https://github.com/Vanilla-OS/almost) által ér 
  el felülírhatatlanságot. Ezt a kelléket a fájlok felülírhatatlan tulajdonságán 
  alapuló, igény szerinti felülírhatatlansághoz írtuk. Ez a megközelítés bármely 
  partíciós sémán, vagy fájlrendszeren működik. Az OSTree még szóba jöhet a jövőben. 
- **Gördülő Kiadás?**<br />
  Nem. A Vanilla OS egy pont-kiadású rendszer és az Ubuntu kiadási ciklust követi.

## Szekciók

- **[Felülírhatatlanság (`almost`)](/almost)**<br />
Az Almost egy kellék a fájlok felülírhatatlan tulajdonságán alapuló, igény 
szerinti felülírhatatlansághoz.

- **[Csomagkezelő (`apx`)](/apx/)**<br />
Az Apx egy olyan csomagkezelő, amely egy kezelt konténerbe enged csomagokat 
telepíteni, anélkül, hogy a hosztrendszert befolyásolná. Alkalmanként, az `apx` 
használatával lehetséges a hosztrendszerre is telepíteni csomagokat.
