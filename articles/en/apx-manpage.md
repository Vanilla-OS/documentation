---
Title: Apx Manpage
Description: Manpage for the Apx utility.
PublicationDate: 2023-09-03
Authors: 
  - Contributors of Vanilla OS
Tags:
  - apx
  - manpage
---

## NAME

```md
Apx is a package manager with support for multiple sources, allowing you to install packages in subsystems.
```

## SYNOPSIS

```md
apx [command] [arguments] [options]
```

## DESCRIPTION

```md
Apx is a package manager with support for multiple sources, allowing you to install packages in subsystems.

Usage:
  apx [command]

Available Commands:
  [subsystem] Work with the specified subsystem, accessing the package manager and environment.
  completion  Generate the autocompletion script for the specified shell
  help        Help about any command
  pkgmanagers Work with the package managers that are available in apx.
  stacks      Work with the stacks that are available in apx.
  subsystems  Work with the subsystems that are available in apx.

Flags:
  -h, --help      help for apx
  -v, --version   version for apx

Use "apx [command] --help" for more information about a command.
```

## COMPLETION

```md
Generate the autocompletion script for apx for the specified shell.
See each sub-command's help for details on how to use the generated script.

Usage:
  apx completion [command]

Available Commands:
  bash        Generate the autocompletion script for bash
  fish        Generate the autocompletion script for fish
  powershell  Generate the autocompletion script for powershell
  zsh         Generate the autocompletion script for zsh

Flags:
  -h, --help   help for completion

Use "apx completion [command] --help" for more information about a command.
```

## PKGMANAGERS

```md
Work with the package managers that are available in apx.

Usage:
  apx pkgmanagers [command]

Available Commands:
  list        List all available package managers.
  new         Create a new package manager.
  rm          Remove the specified package manager.
  show        Show information about the specified package manager.

Flags:
  -h, --help   help for pkgmanagers

Use "apx pkgmanagers [command] --help" for more information about a command.
```

### PKGMANAGERS LIST

```md
List all available package managers.

Usage:
  apx pkgmanagers list [flags]

Flags:
  -h, --help   help for list
  -j, --json   Output in JSON format.
```

### PKGMANAGERS NEW

```md
Create a new package manager.

Usage:
  apx pkgmanagers new [flags]

Flags:
  -y, --assume-yes          Assume yes to all prompts.
  -a, --autoremove string   The command to run to autoremove packages.
  -c, --clean string        The command to run to clean the package manager's cache.
  -h, --help                help for new
  -i, --install string      The command to run to install packages.
  -l, --list string         The command to run to list installed packages.
  -n, --name string         The name of the package manager.
  -S, --need-sudo           Whether the package manager needs sudo to run.
  -p, --purge string        The command to run to purge packages.
  -r, --remove string       The command to run to remove packages.
  -s, --search string       The command to run to search for packages.
  -w, --show string         The command to run to show information about packages.
  -u, --update string       The command to run to update the list of available packages.
  -U, --upgrade string      The command to run to upgrade packages.
```

### PKGMANAGERS RM

```md
Remove the specified package manager.

Usage:
  apx pkgmanagers rm [flags]

Flags:
  -f, --force         Force removal of the package manager.
  -h, --help          help for rm
  -n, --name string   The name of the package manager to remove.
```

### PKGMANAGERS SHOW

```md
Show information about the specified package manager.

Usage:
  apx pkgmanagers show [flags]

Flags:
  -h, --help   help for show
```

## STACKS

```md
Work with the stacks that are available in apx.

Usage:
  apx stacks [command]

Available Commands:
  export      Export the specified stack.
  import      Import the specified stack.
  list        List all available stacks.
  new         Create a new stack.
  rm          Remove the specified stack.
  show        Show information about the specified stack.
  update      Update the specified stack.

Flags:
  -h, --help   help for stacks

Use "apx stacks [command] --help" for more information about a command.
```

### STACKS EXPORT

```md
Export the specified stack.

Usage:
  apx stacks export [flags]

Flags:
  -h, --help            help for export
  -n, --name string     The name of the stack to export.
  -o, --output string   The path to export the stack to.
```

### STACKS IMPORT

```md
Import the specified stack.

Usage:
  apx stacks import [flags]

Flags:
  -h, --help           help for import
  -i, --input string   The path to import the stack from.
```

### STACKS LIST

```md
List all available stacks.

Usage:
  apx stacks list [flags]

Flags:
  -h, --help   help for list
  -j, --json   Output in JSON format.
```

### STACKS NEW

```md
Create a new stack.

Usage:
  apx stacks new [flags]

Flags:
  -y, --assume-yes           Assume yes to all prompts.
  -b, --base string          The base distribution image to use. (For a list of compatible images view: https://distrobox.it/compatibility/#containers-distros)
  -h, --help                 help for new
  -n, --name string          The name of the stack.
  -p, --packages string      The packages to install.
  -k, --pkg-manager string   The package manager to use.
```

### STACKS RM

```md
Remove the specified stack.

Usage:
  apx stacks rm [flags]

Flags:
  -f, --force         Force removal of the stack.
  -h, --help          help for rm
  -n, --name string   The name of the stack to remove.
```

### STACKS SHOW

```md
Show information about the specified stack.

Usage:
  apx stacks show [flags]

Flags:
  -h, --help   help for show
```

### STACKS UPDATE

```md
Update the specified stack.

Usage:
  apx stacks update [flags]

Flags:
  -y, --assume-yes           Assume yes to all prompts.
  -b, --base string          The base subsystem to use.
  -h, --help                 help for update
  -n, --name string          The name of the stack.
  -p, --packages string      The packages to install.
  -k, --pkg-manager string   The package manager to use.
```

## SUBSYSTEMS

```md
Work with the subsystems that are available in apx.

Usage:
  apx subsystems [command]

Available Commands:
  list        List all available subsystems.
  new         Create a new subsystem.
  reset       Reset the specified subsystem.
  rm          Remove the specified subsystem.

Flags:
  -h, --help   help for subsystems

Use "apx subsystems [command] --help" for more information about a command.
```

### SUBSYSTEMS LIST

```md
List all available subsystems.

Usage:
  apx subsystems list [flags]

Flags:
  -h, --help   help for list
  -j, --json   Output in JSON format.
```

### SUBSYSTEMS NEW

```md
Create a new subsystem.

Usage:
  apx subsystems new [flags]

Flags:
  -h, --help           help for new
  -n, --name string    The name of the subsystem.
  -s, --stack string   The stack to use.
```

### SUBSYSTEMS RESET

```md
Reset the specified subsystem.

Usage:
  apx subsystems reset [flags]

Flags:
  -f, --force         Force reset of the subsystem.
  -h, --help          help for reset
  -n, --name string   The name of the subsystem to reset.

```

### SUBSYSTEMS RM

```md
Remove the specified subsystem.

Usage:
  apx subsystems rm [flags]

Flags:
  -f, --force         Force removal of the subsystem.
  -h, --help          help for rm
  -n, --name string   The name of the subsystem to remove.

```

## SEE ALSO

- [`abroot`](abroot)
- [`vso`](vso)

## REPORTING BUGS

Report bugs to the [issue tracker](https://github.com/Vanilla-OS/apx/issues).
