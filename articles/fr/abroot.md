---
Title: Immutabilité (ABRoot) - Vanilla OS
Description: Découvrez comment utiliser ABRoot.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

> Cette documentation fait référence à ABRoot v1, et non à v2. La documentation de la v2 est toujours en cours de rédaction.

`abroot` est un utilitaire qui apporte une atomicité et immutabilité complète en effectuant des transactions entre 2 partitions racines (A⟺B), et permet aussi des transactions sur-demande via un shell transactionnel.

## Fonctionnement

Le système de fichier de Linux est une structure de fichier hiérarchisée contenant la racine et d'autres répertoires.
La racine est le principal répertoire hiérarchique contenant toutes les autres partitions.
Dans les système de fichiers immutables, la partition racine est en lecture seule, empêchant l'installation de packages essentiels, tels que des pilotes dans l'hôte.

`abroot` vous permet d'installer des modules pour le kernel, des pilotes et d'autres packages essentiels sans compromettre l'immutabilité du système de fichiers.

Lorsqu'une commande est executée dans `abroot`, une transaction est initiée dans le shell transactionnel dans la seconde partition racine. Si la transaction réussit, les changements sont appliqués en utilisant une surcouche et synchronisés avec la racine actuelle au redémarrage. Si la transaction échoue, aucun changement n'est appliqué (due à une propriété dite d'atomicité). `abroot` permet aussi des transactions sur-demande en utilisant la commande `abroot shell`.

Les installations de Vanilla OS créent des partitions root et boot pour les deux états (20GO par partition racine) car c'est exigé par `abroot`.

## États

`abroot` a deux états - présent et futur. Lorsque vous êtes dans votre installation de Vanilla OS pour la première fois, l'état initial est A. Lorsque vous redémarrez votre système, l'état commute automatiquement vers B. Lorsque vous installez un package en utilisant `abroot`, il est installé dans la partition racine future et sera synchronisé avec la partition racine actuelle au prochain redémarrage.

## Mises à jour

`abroot` fait fonctionner l'utilitaire `vso` permettant des mises à jour intelligentes automatiques et l'installation de mises à jour en arrière-plan dans la partition racine future, sauvant donc du temps puisqu'une mise à jour hors-ligne pendant le redémarrage n'est pas requise.

## Appellation

Le nom d'ABRoot fait référence aux des partitions racines A et B en transaction (A⟺B).

## Utilisation

- [Manpage](abroot-manpage)
