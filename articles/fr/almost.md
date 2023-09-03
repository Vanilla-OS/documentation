---
Title : Immutabilité (almost) - Vanilla OS
Description : Découvrez comment utiliser Almost, l'utilitaire d'immutabilité à la demande.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

`almost` est un utilitaire qui fournit l'immutabilité à la demande en commutant l'immutabilité
des fichiers et des répertoires à la racine du système. Il fournit également
un moyen de créer des couches au dessus de répertoires immutables, vous permettant de tester
les changements avant de les valider.

Note: `almost` has been replaced with `abroot`.

## Comment ça marche

L'immutabilité dans `almost` est obtenue en placant le drapeau `i` sur tous les fichiers et répertoires dans la racine du système, à l'exception de ceux qui sont utilisés pour le répertoire personnel de l'utilisateur (`/home, /etc, /var`).

La même chose peut être réalisée en utilisant la commande `chattr`, mais `almost` fournit une
cohérence en restaurant l'état par défaut du système après un redémarrage, et
avec des fonctionnalités supplémentaires pour mieux gérer l'immutabilité, par exemple lancer une commande tout en
en désactivant temporairement l'immutabilité.

### Immutabilité à la demande

On parle d'immutabilité *à la demande* car elle peut être activée ou désactivée à tout moment.
L'immutabilité est censée être utilisée comme une mesure de sécurité
pour éviter les modifications accidentelles du système, elle doit donc être activée la plupart du temps.

De par sa nature, `almost` est prêt à l'emploi et fonctionne sur tous les systèmes de fichiers et toutes les configurations.

### Le nom

Le nom `almost` vient du fait qu'il ne s'agit pas d'une solution complète d'immutabilité,
mais plutôt d'un outil pour vous aider à la mettre en place,
tout en étant capable d'effectuer des changements si nécessaire.

## Ce qu'il n'est pas

`almost` n'a pas de support pour les snapshots. Chaque modification apportée au
système est permanente et ne peut être annulée sans restaurer une sauvegarde ou rétrograder le système.
Pour éviter cela, vous devriez toujours tester vos changements en utilisant les couches avant de les valider.
La seule raison de désactiver l'immutabilité serait de vouloir modifier
un fichier de configuration qui ne se trouve pas dans les répertoires communs,
ou pour installer des pilotes. Désactiver l'immutabilité pour installer une application ou une bibliothèque n'est pas recommandée.
Utilisez [`apx`](/docs/apx), [`Flatpak`](/docs/flatpak), [`Snap`](/docs/snap) ou [`AppImage`](/docs/appimage)..

## Utilisation

- [Guide](almost-manpage)
