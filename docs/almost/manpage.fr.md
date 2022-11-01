---
titre : Guide pour Almost - Vanilla OS
description : Guide pour l'utilitaire almost.
---

# Guide pour `almost`

## NOM
```
almost - un outil d'immuabilité et de superposition à la demande basé sur l'attribut de fichier (i)mmutable et tmpfs.
```

## SYNOPSIS
```
almost [OPTIONS] [COMMAND] [ARGS]
```

## DESCRIPTION
```
almost est un utilitaire qui fournit une immutabilité à la demande en basculant l'immutabilité des fichiers et des répertoires à la racine du système. Il fournit également un moyen de créer des couches au-dessus des répertoires immuables, vous permettant de tester les changements avant de les valider.

Options:
	--help/-h   affiche ce message
	--verbose/-v    sortie détaillée
	--version/-V		afficher la version

Commands:
	enter			définir le système de fichiers comme ro ou rw jusqu'au redémarrage
	config			affiche la configuration actuelle
	check			vérifie si le système de fichiers est en lecture seule ou en lecture-écriture
	run			exécute une commande en mode lecture-écriture et revient en mode lecture seule à la fin de la commande.
```

## ENTER
```
Définir le système de fichiers en lecture seule ou en lecture-écriture jusqu'au redémarrage.

Le passage du système de fichiers en mode lecture-écriture peut présenter un risque de
sécurité, soyez prudent lorsque vous utilisez cette commande..

Utilisation:
    enter [options] [command]

Options:
	--help/-h		affiche ce message
	--verbose/-v		sortie détaillée

Commandes:
	ro			définit le système de fichiers en lecture seule
	rw			définit le système de fichiers en lecture-écriture
	default			définit le système de fichiers tel que défini dans le fichier de configuration

Exemples:
	almost enter ro
	almost enter rw
```

## CONFIG
```
Gère et affiche la configuration actuelle.

Utilisation:
    config [options] [command]

Options:
    --help/-h		affiche ce message

Commandes:
    set [key] [value]	définit une valeur de configuration

Exemples:
    almost config
    almost config set Almost::DefaultMode 1
```

## CHECK
```
Vérifie si le système de fichiers est en lecture seule ou en lecture-écriture.

Utilisation:
check [options] [command]
Options:
	--help/-h		affiche ce message
Exemples:
	almost check
```

## RUN
```
Exécute une commande en mode lecture-écriture et revient en mode lecture seule après la fin de la commande.

Utilisation:
    run [command]
Options:
	--help/-h		affiche ce message
	--verbose/-v		sortie détaillée
Exemples:
    almost run ls
```

## VOIR AUSSI
- [`apx`](/docs/apx)

## DIAGNOSTICS
```
almost renvoie un 0 en cas de succès, 1 en cas d'erreur.
```

## AUTEUR
```
Contributeurs de Vanilla OS
```

## RAPPORT DE BOGUES
Rapportez les bogues sur le [issue tracker](https://github.com/Vanilla-OS/almost/issues).
