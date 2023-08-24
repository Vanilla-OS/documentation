---
Title: Apx Manpage
Description: Manpage for the Apx utility.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

# Manpage `apx`

## NAME

```text
`apx` - the Vanilla OS package manager that is easy to use with support for installing packages from multiple sources inside containers without altering the root filesystem.
```

## SYNOPSIS

```text
apx [options] [command] [arguments]
```

## DESCRIPTION

```markdown
apx is a wrapper around multiple package managers to install packages and run commands inside a managed container.

Usage:
    apx [options] [command] [arguments]

Options:
    -h, --help      Show this help message and exit
    -v, --version   Show version and exit
    --aur           Install packages from the AUR repository
    --dnf           Install packages from the Fedora repository

Commands:
    autoremove      Remove all unused packages
    clean           Clean the apx package manager cache
    enter           Enter the container shell
    export          Export/Recreate a program's desktop entry from the container
    help            Show this help message and exit
    init            Initialize a managed container
    install         Install packages inside the container
    list            List installed packages
    purge           Purge packages from the container
    run             Run a command inside the container
    remove          Remove packages from the container
    search          Search for packages
    show            Show details about a package
    unexport        Unexport/Remove a program's desktop entry
    update          Update the list of available packages
    upgrade         Upgrade the system by installing/upgrading available packages
```

## AUTOREMOVE

```markdown
Description: 
    Remove all unused packages automatically.
Usage:
    apx autoremove [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx autoremove
```

## CLEAN

```markdown
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

```markdown
Description: 
    Enter in the container shell.

Usage:
    apx enter [options]

Options:
    -h, --help            Show this help message and exit
```

## EXPORT

```markdown
Description: 
    Export/Recreate a program's desktop entry from a managed container.

Usage:
    apx export <program> [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx export htop
```

## INIT

```markdown
Description: 
    Initialize the managed container.

Usage:
    apx init [options]

Options:
    -h, --help            Show this help message and exit
```

## INSTALL

```markdown
Description: 
    Install packages inside a managed container.

Usage:
    apx install [options] <packages>

Options:
    -h, --help            Show this help message and exit
    -y, --assume-yes      Proceed without manual confirmation.
    -f, --fix-broken      Fix broken deps before installing
    --no-export           Do not export a desktop entry after the installation. 
    --sideload [path]     Install a package from a local file.

Examples:
    apx install htop git
    apx install --sideload /path/to/file.deb
```

## LIST

```markdown
Description: 
    List installed packages.

Usage:
    apx list [options]

Options:
    -h, --help            Show this help message and exit
```

## PURGE

```markdown
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

```markdown
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

```markdown
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

```markdown
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

```markdown
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

```markdown
Description:
    Unexport/Remove a program's desktop entry from a managed container.

Usage:
    apx unexport <program> [options]

Options:
    -h, --help            Show this help message and exit

Examples:
    apx unexport htop
```

## UPDATE

```markdown
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

```markdown
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

```markdown
Description:
    Display the version number of apx.

Usage:
    apx --version
    apx -v
```

## SEE ALSO

- [`abroot`](abroot)
- [`vso`](vso)

## AUTHOR

```text
Contributors of Vanilla OS
```

## REPORTING BUGS

Report bugs to the [issue tracker](https://github.com/Vanilla-OS/apx/issues).
