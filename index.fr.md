---
titre: Documentation de Vanilla OS
description: Découvrez comment utiliser Vanilla OS et tous ses outils et paramètres.
---

# Vanilla OS
Goûtez l'expérience GNOME Vanilla sur Ubuntu avec un peu de piment.

## FAQ
Réponses aux questions les plus fréquemment posées (même si le projet est nouveau).
- **Pourquoi une nouvelle distribution?**\
  Vanilla OS est né de la nécessité de disposer d'une distribution Linux basée sur Ubuntu qui 
  qui fournirait GNOME vanilla sans aucune modification de l'expérience utilisateur. 
  Plus tard, son champ d'application a été étendu pour expérimenter certains outils et technologies, tels que Almost (immuabilité à la demande) et 
  Apx (le sous-système basé sur Distrobox).
- **Est-ce que Vanilla OS utilise OSTree ?**\
  Non. Vanilla OS réalise l'immuabilité par le biais de [`almost`](https://github.com/Vanilla-OS/almost). 
  Nous avons écrit cet utilitaire pour l'immuabilité à la demande basée sur l'attribut d'immuabilité des fichiers. 
  Cette approche fonctionne sur n'importe quelle partition 
  schéma/système de fichiers. OSTree peut encore être considéré dans le futur.
- **Rolling Release?**\
  Non. Vanilla OS est une point release et suit le cycle de publication d'Ubuntu.

## Sections
- **[Immutabilité (`almost`)](/docs/almost)**\
Almost est un utilitaire pour l'immutabilité à la demande basée sur
sur l'attribut d'immuabilité des fichiers.

- **[Gestionnaire de paquets (`apx`)](/docs/apx)**\
Apx est un gestionnaire de paquets qui vous permet d'installer et de gérer des paquets dans un conteneur géré, sans affecter le système hôte.
Occasionnellement, il est possible d'utiliser `apx` pour installer des paquets sur le système hôte également.
