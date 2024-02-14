---
Title: Page de manuel (manpage) pour apx - Vanilla OS
Description: Page de manuel pour l'utilitaire apx.
PublicationDate: 2023-06-10
Authors: 
  - Contributors of Vanilla OS
---

## NOM

```md
`apx` - Le gestionnaire de programme de VanillaOS qui est facile à utiliser et qui supporte l'installation de programmes de plusieurs sources depuis un conteneur sans altérer le système de fichiers administrateur.
```

## SYNOPSIS

```md
apx [options] [commande] [arguments]
```

## DESCRIPTION

```md
apx est un "wrapper" de plusieurs gestionnaires de programme pour installer des programmes et exécuter des commandes à l'intérieur d'un conteneur.

Usage:
    apx [options] [commande] [arguments]

Options:
    -h, --help      Montre ce message d'aide
    -v, --version   Montre la version et quitte
    --aur           Installe un programme depuis le dépot AUR
    --dnf           Installe un programme depuis le dépot de Fedora

Commandes:
    autoremove      Enlève tout les programmes inutilisés
    clean           Nettoie le cache de apx
    enter           Entre dans le shell du container
    export          Exporte/Recrée une entrée sur le bureau depuis le conteneur  
    help            Montre ce message et quitte
    init            Initialise un conteneur géré
    install         Installe un programme dans le conteneur
    list            Liste les programmes installés
    log             Montre le registre
    purge           Purge les programmes du conteneur
    run             Exécute une commande dans le conteneur
    remove          Supprime un programme d'un conteneur
    search          Cherche un programme
    show            Montre les détails d'un programme
    unexport        Désexporte/Supprime une entrée d'un programme sur le bureau
    update          Met à jour la liste de programmes
    upgrade         Met à jour le système en installant/mettant à jour les programmes disponibles
```

## AUTOREMOVE

```md
Description: 
    Enlève les programmes inutiles automatiquement.

Utilisation:
    apx autoremove [options]

Options:
    -h, --help            Montre ce message et quitte

Exemples:
    apx autoremove
```

## CLEAN

```md
Description: 
    Nettoie le cache de apx.

Utilisation:
    apx clean [options]

Options:
    -h, --help            Montre ce message et quitte

Exemples:
    apx clean
```

## ENTER

```md
Description: 
    Entre dans le shell du conteneur.

Utilisation:
    apx enter [options]

Options:
    -h, --help            Montre ce message et quitte
Exemples:
	apx enter --apt        Entre dans le shell du container apt
	apx enter --aur			Entre dans le shell du container aur
```

## EXPORT

```md
Description: 
    Exporte/Recrée l'entrée bureau d'un programme depuis un conteneur.

Usage:
    apx export <programme> [options]

Option:
    -h, --help            Montre ce message et quitte

Exemple:
    apx export htop
```

## INIT

```md
Description: 
    Initialise un conteneur.

Utilisation:
    apx init [options]

Options:
    -h, --help            Montre ce message et quitte
```

## INSTALL

```md
Description: 
    Installe un programme dans un conteneur.

Usage:
    apx install [options] <programme>

Options:
    -h, --help            Montre ce message et quitte
    -y, --assume-yes      Effectue sans confirmation manuelle.
    -f, --fix-broken      Répare les dépendances avant l'installation  
    --no-export           N'exporte pas sur le bureau après l'installation. 
    --sideload [path]     Installe un programme depuis un fichier local.

Exemples:
    apx install htop git
    apx install --sideload /chemain/vers/fichier.deb
```

## LIST

```md
Description: 
    Liste les programmes installés.

Utilisation:
    apx list [options]

Options:
    -h, --help            Montre ce message et quitte
```

## PURGE

```md
Description: 
    Purge les programmes dans un conteneur.

Utilisation:
    apx purge <programmes> [options]

Options:
    -h, --help            Montre ce message et quitte

Exemples:
    apx purge htop
```

## REMOVE

```md
Description:
    Enlève un programme d'un conteneur.

Utilisation:
    apx remove <programmes> [options]

Options:
    -h, --help            Montre ce message et quitte

Exemples:
    apx remove htop
```

## RUN

```md
Description: 
    Exécute un programme dans un conteneur.

Utilisation:
    apx run <programme> [options]

Options:
    -h, --help            Montre ce message et quitte

Exemples:
    apx run htop
```

## SEARCH

```md
Description: 
    Cherche un programme dans un conteneur.

Utilisation:
    apx search <programme> [options]

Options:
    -h, --help            Montre ce message et quitte

Exemples:
    apx search htop
```

## SHOW

```md
Description: 
    Affiche les détails d'un programme.

Utilisation:
    apx show <programme> [options]

Options:
    -h, --help            Montre ce message et quitte

Exemple:
    apx show htop
```

## UNEXPORT

```md
Description:
    Désexporte/Supprime un entré bureau d'un programme dans un conteneur.

Utilisation:
    apx unexport <programme> [options]

Options:
    -h, --help            Montre ce message et quitte

Exemples:
    apx unexport htop
```

## UPDATE

```md
Description: 
    Met à jour la liste de programmes.

Utilisation:
    apx update [options]

Options:
    -h, --help            Montre ce message et quitte

Exemples:
    apx update
```

## UPGRADE

```md
Description: 
    Mets à jour le systeme en installant/mettant à jour les programmes disponibles.

Utilisation:
    apx upgrade [options]
  
Options:
    -h, --help            Montre ce message et quitte

Exemples:
    apx upgrade
```

## VERSION

```md
Description:
    Montre le numéro de version d'apx.

Utilisation:
    apx --version
    apx -v
```

## Voir aussi

- [`abroot`](abroot)
- [`vso`](vso)

## AUTEURS

```md
Contributeurs de Vanilla OS
Traduit en français par aWildJumpyGame
```

## SIGNALER DES BOGUES

Signaler un bogue au [traqueur de problèmes](https://github.com/Vanilla-OS/apx/issues).
