---
titre : Gestionnaire de paquets (apx) - Vanilla OS
description : Découvrez comment utiliser apx, le gestionnaire de paquets de Vanilla OS.
---

# Gestionnaire de paquets (`apx`)
`apx` est le gestionnaire de paquets de Vanilla OS. Il est censé être facile à utiliser, 
mais aussi puissant, avec un support pour l'installation de paquets depuis de multiples sources sans altérer le système de fichiers racine.

## Comment ça marche
`apx` introduit un tout nouveau paradigme dans la gestion des paquets. 
L'idée est d'utiliser votre système uniquement comme une boîte pour stocker vos fichiers,
en le laissant propre de paquets et de limiter le risque de casse dû 
à des paquets incompatibles, mal construits ou conflictuels.

Ceci est réalisé en installant des logiciels à l'intérieur d'un ou plusieurs conteneurs "gérés", 
qui sont entièrement gérés par `apx` et qui ont un accès restreint aux ressources de votre système, 
tout en étant capable d'utiliser les mêmes pilotes, serveur d'affichage, etc.

Votre répertoire personnel est mappé à l'intérieur du conteneur, 
vous pouvez donc accéder à vos fichiers de configuration, vos préférences et autres données vitales. 
nécessaire par les paquets installés, ainsi que la possibilité d'accéder à vos propres fichiers depuis le logiciel 
installés, par exemple en ouvrant un fichier dans LibreOffice.

### Système hôte
Bien que l'installation de logiciels sur l'hôte soit contraire à l'idéologie du projet, 
il existe des cas où cela ne peut être évité, par exemple lorsque vous devez 
installer un module du noyau.

Dans de tels cas, vous utiliserez le drapeau `--sys` pour contourner le conteneur et 
installer directement sur l'hôte, *mais sachez que ce n'est pas recommandé*. `apx` 
fonctionne avec [`almost`](/docs/almost) pour désactiver temporairement l'immutabilité, 
vous permettant d'installer les paquets nécessaires et de restaurer le système par la suite.

### Sources multiples
Par défaut, `apx` fournit un conteneur basé sur votre distribution Linux (Ubuntu 22.10 pour Vanilla OS 22.10) 
et englobe toutes les commandes du gestionnaire de paquets de la distribution (`apt` pour Ubuntu).

Néanmoins, il est toujours possible d'installer des paquets provenant d'autres distributions 
en utilisant d'autres gestionnaires de paquets, par exemple, en utilisant le drapeau `--aur`, 
un deuxième conteneur basé sur Arch Linux sera créé. 
Ici, `apx` va gérer les logiciels de l'AUR (et de Pacman), en l'intégrant toujours au système hôte.

Pour des raisons de contrôle de qualité et de tests, nous avons choisi de limiter cette fonctionnalité 
à des implémentations spécifiques. Actuellement, seul le drapeau `--aur` est supporté, mais 
mais nous prévoyons d'implémenter le support pour le gestionnaire de paquets Nix également.

### Le nom
Le nom `apx` provient de **apt (Advanced Packaging Tool)**, le gestionnaire de paquets 
paquet utilisé par Debian et ses dérivés, et **X**, qui doit être considéré comme 
2 lignes (hôte et conteneur) qui se chevauchent, où le conteneur est au dessus, 
ce qui veut dire qu'il se trouve au-dessus du système hôte.

## Usage
- [Guide](/docs/apx/manpage)
