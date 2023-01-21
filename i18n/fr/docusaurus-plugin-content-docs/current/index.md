---
title: Documentation de Vanilla OS
description: Découvrez comment utiliser Vanilla OS et tous ses outils et paramètres.
sidebar_position: 1
---

# Vanilla OS

Goûtez à l'expérience épicée d'un GNOME Vanilla sur Ubuntu.

## FAQ

Réponses aux questions les plus fréquemment posées (alors même que le projet est tout nouveau).
- **Pourquoi une nouvelle distribution ?**<br />
  Vanilla OS est né de la nécessité de disposer d'une distribution Linux basée sur Ubuntu qui 
  qui fournirait un GNOME standard sans aucune modification de l'expérience utilisateur. 
  Plus tard, son champ d'application a été étendu pour expérimenter certains outils et technologies, tels qu'Almost (immutabilité à la demande) et 
  Apx (le sous-système basé sur Distrobox).
- **Est-ce que Vanilla OS utilise OSTree ?**<br />
  Non. Vanilla OS accomplit l'immutabilité par le biais d'[`almost`](https://github.com/Vanilla-OS/almost). 
  Nous avons écrit cet utilitaire pour une immutabilité à la demande basée sur l'attribut d'immutabilité des fichiers. 
  Cette approche fonctionne avec n'importe quel schéma de partition ou système de fichiers. L'utilisation d'OSTree est encore envisageable à l'avenir.
- **Version rolling ?**<br />
  Non. Vanilla OS fonctionne par version intermédiaire et suit le cycle de publication d'Ubuntu.

## Sections

- **[Immutabilité (`almost`)](/almost)**<br />
Almost est un utilitaire pour l'immutabilité à la demande basée sur l'attribut d'immutabilité des fichiers.

- **[Gestionnaire de paquets (`apx`)](/apx/)**<br />
Apx est un gestionnaire de paquets qui vous permet d'installer et de gérer des paquets dans un conteneur contrôlé, sans affecter le système hôte.
Occasionnellement, il est possible d'utiliser `apx` pour installer des paquets sur le système hôte.
