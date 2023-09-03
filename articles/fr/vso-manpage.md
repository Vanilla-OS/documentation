---
Title: Manpage vso - Vanilla OS
Description: Manpage pour l'utilitaire vso.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

## NOM

```md
VSO est un utilitaire qui vous permet de réaliser des taches de maintenance sur votre installation Vanilla OS.
```

## SYNOPSIS

```md
vso [options] [commande] [arguments]
```

## DESCRIPTION

```md
Utilisation: 
    vso [options] [commande] [arguments]

Options:
    -h, --help            Afficher ce message d'aide et quitter

Commandes:
    config                  Configurer VSO
    create-task             Créer une nouvelle tache
    delete-task             Supprimer une tache
    developer-program       Rejoindre le programme développeurs
    help                    Afficher ce message d'aide et quitter
    list-tasks              Lister toutes les taches
    rotate-tasks            Faire tourner les taches
    trigger-update          Actionner une mise à jour système
    version                 Afficher la version et quitter
```

## CONFIGURATION

```md
Description: 
    Configurer VSO

Utilisation:
    vso config [options] [commande]

Options:
    --help/-h           afficher ce message
    --assume-yes/-y     supposer oui à toutes les questions

Commandes:
    show                afficher la configuration actuelle
    get <key>           obtenir une valeur de configuration
    set <key> <value>   définir une valeur de configuration

Exemples:
    vso config get updates::schedule
    vso config set updates::schedule weekly
```

## CREER UNE TACHE

```md
Description: 
    Créer une nouvelle tache

Utilisation:
    vso create-task [options] [arguments]

Options:
    --help/-h               afficher ce message

Arguments:
    --name/-n               nom de la tache
    --description/-d        description de la tache
    --need-confirm          demander confirmation avant d'exécuter la tache
    --command/-c            commande pour exécuter
    --after-task            exécuter la tache après une autre tache
    --after-task-success    exécuter la tache après une autre tache si elle a réussi
    --after-task-failure    exécuter la tache après une autre tache si elle a échoué
    --every/-e              exécuter la tache toute les X (minutes, heures, jours)
    --at/-a                 exécuter la tache à un temps spécifique (hh:mm)
    --on-boot               exécuter la tache au démarrage
    --on-shutdown           exécuter la tache à l'arrêt
    --on-login              exécuter la tache à la connexion
    --on-network            exécuter la tache à la connexion réseau
    --on-disconnect         exécuter la tache à la déconnexion réseau
    --on-battery            exécuter la tache sur batterie
    --on-low-battery        exécuter la tache sur batterie faible (20%)
    --on-charge             exécuter la tache sur batterie en charge
    --on-full-battery       exécuter la tache sur batterie pleine
    --on-condition-command  exécuter la tache sur commande conditionnelle
    --on-process            exécuter la tache lorsqu'un processus apparait

Exemples:
    vso create-task -n "Batterie pleinement chargée" -d "notifier lors du chargement complet" -c "notify-send 'Batterie pleinement chargée'" --on-full-battery
    vso create-task -n "Lancer-terminal" -d "Lancer le terminal lors du lancement des Paramètres" -c "kgx" --on-process gnome-control-center
```

## SUPPRIMER UNE TACHE

```md
Description: 
    Supprimer une tache

Utilisation:
    vso delete-task [tache] [options]

Options:
    --help/-h       afficher ce message

Exemples:
    vso delete-task ma-tache
    vso delete-task "ma tache"
```

## PROGRAMME DEVELOPPEURS

```md
Description: 
    Rejoindre le programme développeurs

Utilisation:
    vso developer-program [options]

Options:
    --help/-h       afficher ce message

Exemples:
    vso developer-program
```

## LISTER LES TACHES

```md
Description: 
    Lister toutes les taches

Usage:
    vso list-tasks [options]

Options:
    --help/-h       afficher ce message

Examples:
    vso list-tasks
```

## FAIRE TOURNER LES TACHES

```md
Description: 
    Faire tourner les taches

Usage:
    vso rotate-tasks [options]

Options:
    --help/-h       afficher ce message

Examples:
    vso rotate-tasks
```

## ACTIONNER UNE MISE A JOUR

```md
Description: 
    Actionner une mise à jour système

Usage:
    vso trigger-update [options]

Options:
    --help/-h       afficher ce message
    --now           actionner une mise à jour système immédiatement

Examples:
    vso trigger-update --now
```

## CONSULTER EGALEMENT

- [`apx`](apx)
- [`abroot`](abroot)

## AUTEUR

```md
Les contributeurs de Vanilla OS, dont D-Maxwell (traducteur)
```

## SIGNALER DES BUGS

Signalez des bugs sur le [recenseur de problèmes](https://github.com/Vanilla-OS/vanilla-system-operator/issues).
