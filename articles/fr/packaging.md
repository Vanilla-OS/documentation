---
Title: Packaging - Vanilla OS
Description: Découvrez comment packager des programmes et des librairies pour Vanilla OS.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

# Packaging

Le packaging est le processus de création d'un package pour un programme ou une librairie,
de manière à ce qu'il puisse être installé sur une distribution. Vanilla OS a une
disposition de système de fichiers racine inconventionnel, qui requiert quelques
considérations et de suivre quelques règles.

## Quand Packager?

Vanilla OS est une distribution transactionnelle, ce qui veut dire qu'elle
reçoit des mises à jour par des transactions. Le processus est géré par [ABRoot](/docs/ABRoot),
qui requiert un redémarrage pour appliquer les modifications. Cela veut dire
que l'utilisateur devra redémarrer son système après avoir installé un
package, et ce n'est pas idéal. La partition racine est également très petite,
c'est intentionnel pour empêcher l'utilisateur d'installer trop de packages,
ce qui exposerait le système à des failles de vulnérabilités et complexifierait
les transactions.

C'est pourquoi, il est recommandé de ne packager que les programmes et librairies
essentiels. Pour mieux comprendre ce qui est essentiel, vous pouvez vous référencer
au tableau suivant:

| Programme | Essentiel | Raison                                                                                                                                                                                                                                                        |
| --------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Chromium  | Non       | C'est un navigateur web, ce qui n'est pas essentiel au système et peut être installé via [Apx](/docs/apx), [Flatpak](https://handbook.vanillaos.org/2022/12/09/install-flatpaks.html), [Snap](https://snapcraft.io/) ou [AppImage](https://appimage.org/).    |
| fuse      | Oui       | C'est un pilote de périphérique, ce qui est essentiel au fonctionnement d'AppImage, et doit également être installé en dehors d'un conteneur Apx.                                                                                                             |
| GIMP      | Non       | C'est un éditeur graphique, ce qui n'est pas essentiel au système et peut être installé via [Apx](/docs/apx), [Flatpak](https://handbook.vanillaos.org/2022/12/09/install-flatpaks.html), [Snap](https://snapcraft.io/) ou [AppImage](https://appimage.org/). |

## Règles de Packaging

Cette section est organisée en plusieurs sous-sections, chacune décrivant
un aspect différent du processus de packaging.

### Appellation

Il n'y a pas de restrictions sur le nom d'un package, mais il est recommandé
d'utiliser le même nom que le projet en amont. Ex. si le projet en amont est
appelé `foo`, le package devrait s'appeller `foo`, et pas `bar`. C'est
important car cela permet à l'utilisateur d'aisément identifier le package.

### Versionnage

La version du package devrait être la même que la version du projet en amont,
avec quelques changements mineurs si nécessaire. Par exemple, si la version
en amont est `1.2.3`, la version du package devrait être `1.2.3`, et pas `2.00`.
Si le package comporte des changements mineurs, la version devrait être `1.2.3-1`,
`1.2.3-2`, etc. La version ne doit jamais aller en arrière ou en avant de la
version en amont.

### Stockage

Certaines applications requièrent beaucoup de stockage, et cela peut être un
problème pour Vanilla OS, qui a une petite partition racine. Si l'application
ne peut pas être installée dans le conteneur Apx ou de n'importe quelle autre
manière, il est recommandé de modifier son comportement pour localiser ses
données dans le répertoire utilisateur personnel ou dans la partition `/home`,
qui a beaucoup plus de stockage.

C'est aussi une bonne habitude, puisque cela permet à l'utilisateur de
sauvegarder les données de l'application, et aussi de facilement retirer
l'application sans perdre de données.
