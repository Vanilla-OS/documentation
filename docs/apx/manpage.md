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
apx [options] [command] [arguments]
```

## DESCRIPTION

```
apx is a wrapper around multiple package managers to install packages and run commands inside a managed container.

Usage:
	apx [options] [command] [arguments]

Options:
	-h, --help    Show this help message and exit
	-v, --version Show version and exit
	--aur	    Install packages from the AUR repository
	--dnf	    Install packages from the Fedora repository

Commands:
    autoremove  Remove all unused packages
	clean       Clean the apx package manager cache
	enter       Enter the container shell
	export      Export/Recreate a program's desktop entry from the container
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
Description: 
	Remove all unused packages automatically.
Usage:
    apx autoremove [options]

Options:
    -h, --help            Show this help message and exit

Usage:
    apx autoremove
```

## CLEAN

```
Description: 
    Clean the apx package manager cache.

Usage:
    apx clean [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx clean
```

## ENTER

```
Description: 
	Enter in the container shell.

Usage:
    apx enter [options]

Options:
    -h, --help            Show this help message and exit
```

## EXPORT

```
Description: 
    Export/Recreate a program's desktop entry from a managed container.

Usage:
    apx export <program> [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx export htop
```

## HELP

```
Description:
    Display help message.

Usage:
    apx --help
```

## INIT
    
```
Description: 
	Initialize the managed container.

Usage:
    apx init [options]

Options:
    -h, --help            Show this help message and exit
```

## INSTALL

```

Description: 
	Install packages inside managed containers that are tightly integrated with the system. For Graphical GUI packages, a `.desktop` entry file is automatically created and added to the GNOME application menu. A list of installed GUI packages can also be found in the Subsystem menu of Vanilla Control Center.

Usage:
    apx install [options] <packages>

Options:
    -h, --help            Show this help message and exit
    -y, --assume-yes      Proceed without manual confirmation.
    -f, --fix-broken      Fix broken deps before installing
    --no-export           Do not export a desktop entry after the installation. --sideload [path]     Install a package from a local file.

Examples:
    apx install htop git
    apx install --sideload /path/to/file.deb
```

## LIST

```
Description: 
	List installed packages.

Usage:
    apx list [options]

Options:
    -h, --help            Show this help message and exit
```

## PURGE

```
Description: 
	Purge packages inside a managed container.

Usage:
    apx purge <packages> [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx purge htop
```

## REMOVE

```
Description:
	Remove packages inside a managed container.

Usage:
    apx remove <packages> [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx remove htop
```

## RUN

```
Description: 
	Run a program inside a managed container.

Usage:
    apx run <program> [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx run htop
```

## SEARCH

```
Description: 
	Search for packages in a managed container.

Usage:
    apx search <packages> [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx search htop
```

## SHOW

```
Description: 
	Show details about a package.

Usage:
    apx show <package> [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx show htop
```

## UNEXPORT

```
Unexport/Remove a program's desktop entry from a managed container.

Usage:
    apx unexport <program> [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx unexport htop
```

## UPDATE

```
Description: 
	Update the list of available packages.

Usage:
    apx update [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx update
```

## UPGRADE

```
Description: 
	Upgrade the system by installing/upgrading available packages.

Usage:
    apx upgrade [options]
  
Options:
    -h, --help            Show this help message and exit

Examples:
    apx upgrade
```

## VERSION

```
Description:
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
