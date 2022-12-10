---
title: Manpage apx - Vanilla OS
description: Manpage for the apx utility.
---

# Manpage `apx`

## NAME

```
`apx` - the Vanilla OS package manager that is easy to use with support for installing packages from multiple sources inside containers without altering the root filesystem.
```

## SYNOPSIS

```
apx [OPTIONS] [COMMAND] [ARGS]
```

## DESCRIPTION

```
apx is a wrapper around multiple package managers to install packages and run commands inside a managed container.

Usage: apx [options] [command] [arguments]

Options:
  -h, --help    Show this help message and exit
  -v, --version Show version and exit
  --aur         Install packages from the AUR repository
  --dnf         Install packages from the Fedora repository

Commands:
    autoremove  Remove all unused packages
    clean       Clean the apx package manager cache
    enter       Enter the container's shell
    export      Export/Recreate a program's desktop entry from a managed container
    help        Show this help message and exit
    init        Initialize a managed container
    install     Install packages inside the container
    list        List installed packages
    log         Show logs
    purge       Purge packages from the container
    run         Run a command inside the container
    remove      Remove packages from the container
    search      Search for packages
    show        Show details about a package
    unexport    Unexport/Remove a program's desktop entry
    update      Update the list of available packages
    upgrade     Upgrade the system by installing/upgrading available packages
    version     Show version and exit
```

## AUTOREMOVE

```
Remove all unused packages automatically.

Usage:
    apx autoremove
    apx --aur autoremove
    apx --dnf autoremove
```

## CLEAN

```
Clean the apx package manager cache.

Usage:
    apx clean
    apx --aur clean
    apx --dnf clean [arguments]

Examples:
    apx clean
    apx --aur clean
    apx --dnf clean all
```

## ENTER

```
Enter the container shell.

Usage:
    apx enter
    apx --aur enter
    apx --dnf enter
```

## EXPORT

```
Export/Recreate a program's desktop entry from a managed container.

Usage:
    apx export <program>
    apx export --aur <program>
    apx export --dnf <program>

Examples:
    apx export htop
    apx export --aur htop
    apx export --dnf firefox
```

## HELP

```
Display help message.

Usage:
    apx --help
```

## INIT
    
```
Initialize the managed container.

Usage:
    apx init
```

## INSTALL

```
Install packages inside managed containers that are tightly integrated with the system. For Graphical GUI packages, a `.desktop` entry file is automatically created and added to the GNOME application menu. A list of installed GUI packages can also be found in the Subsystem menu of Vanilla Control Center.

Usage:
  apx install <packages>
  apx --aur install <packages>
    
Examples:
    apx install htop git
    apx --aur install htop
    apx --dnf install htop
```

## LIST

```
List installed packages.

Usage:
    apx list
    apx --aur list
    apx --dnf list
```

## PURGE

```
Purge packages inside a managed container.

Usage:
    apx purge <packages>
    apx --aur purge <packages>
    apx --dnf purge <packages>

Examples:
    apx purge htop
    apx --aur purge htop
    apx --dnf purge htop
```

## REMOVE

```
Remove packages inside a managed container.

Usage:
    apx remove <packages>
    apx remove --aur <packages>
    apx remove --dnf <packages>

Examples:
    apx remove htop
    apx --aur remove htop
    apx --dnf remove htop
```

## RUN

```
Run a program inside a managed container.

Usage:
    apx run <program>
    apx --aur run <program>
    apx --dnf run <program>

Examples:
    apx run firefox
    apx --aur run neofetch
    apx --dnf run tldr
```

## SEARCH

```
Search for packages in a managed container.

Usage:
    apx search <packages>
    apx --aur search <packages>
    apx --dnf search <packages>

Examples:
    apx search htop
    apx --aur search htop
    apx --dnf search dnf
```

## SHOW

```
Show details about a package.

Usage:
    apx show <package>
    apx --aur show <package>
    apx --dnf show <package>

Examples:
    apx show htop
    apx --aur show htop
    apx --dnf show htop
```

## UNEXPORT

```
Unexport/Remove a program's desktop entry from a managed container.

Usage:
    apx unexport <program>
    apx unexport --aur <program>
    apx unexport --dnf <program>

Examples:
    apx unexport htop
    apx unexport --aur htop
    apx unexport --dnf htop
```

## UPDATE

```
Update the list of available packages.

Usage:
    apx update
    apx --aur update
    apx --dnf update
```

## UPGRADE

```
Upgrade the system by installing/upgrading available packages.

Usage:
    apx upgrade
    apx --aur upgrade
    apx --dnf upgrade
```

## VERSION

```
Display the version number of apx.

Usage:
    apx --version
```

## SEE ALSO

- [`ABRoot`](/docs/ABRoot)

## AUTHOR

```
Contributors of Vanilla OS
```

## REPORTING BUGS

Report bugs to the [issue tracker](https://github.com/Vanilla-OS/apx/issues).
