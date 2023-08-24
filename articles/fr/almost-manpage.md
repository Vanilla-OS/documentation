---
Title : Guide pour almost - Vanilla OS
Description : Guide pour l'utilitaire almost.
Authors: Contributors of Vanilla OS
---

# Guide pour `almost`

Note: `almost` has been replaced with `abroot`.

## NOM

```
almost - un outil d'immuabilité à la demande et de superposition basé sur l'attribut de fichier (i)mmutable et tmpfs.
```

## SYNOPSIS

```
almost [OPTIONS] [COMMANDE] [ARGUMENTS]
```

## DESCRIPTION

```
almost est un utilitaire qui fournit une immutabilité à la demande en commutant l'immutabilité des fichiers et des répertoires à la racine du système. Il fournit également un moyen de créer des couches au-dessus des répertoires immutables, vous permettant de tester les changements avant de les valider.

Options:
	--help/-h   		affiche ce message
	--verbose/-v    	sortie détaillée
	--version/-V		afficher la version

Commandes:
	enter			définit le système de fichiers en lecture seule ou lecture-écriture jusqu'au redémarrage
	config			affiche la configuration actuelle
	check			vérifie si le système de fichiers est en lecture seule ou en lecture-écriture
	run			exécute une commande en mode lecture-écriture et revient en mode lecture seule à la fin de la commande.
```

## ENTER

```
Définit le système de fichiers en lecture seule ou en lecture-écriture jusqu'au redémarrage.

Le passage du système de fichiers en mode lecture-écriture peut présenter un risque de
sécurité, soyez prudent lorsque vous utilisez cette commande..

Utilisation:
    enter [options] [commande]

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
    config [options] [commande]

Options:
    --help/-h		affiche ce message

Commandes:
    set [clé] [valeur]	définit une valeur de configuration

Exemples:
    almost config
    almost config set Almost::DefaultMode 1
```

## CHECK

```
Vérifie si le système de fichiers est en lecture seule ou en lecture-écriture.

Utilisation:
check [options] [commande]

Options:
	--help/-h		affiche ce message
	
Exemples:
	almost check
```

## RUN

```
Exécute une commande en mode lecture-écriture et revient en mode lecture seule après la fin de la commande.

Utilisation:
    run [commande]
    
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

Rapportez les bogues via le [suivi des problèmes](https://github.com/Vanilla-OS/almost/issues).
