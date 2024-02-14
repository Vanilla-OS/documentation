---
Title: ABRoot Manpage
Description: Manpage for the ABRoot utility.
PublicationDate: 2023-08-29
Authors: 
  - Contributors of Vanilla OS
Tags:
  - abroot
  - manpage
---

## NAME

```md
ABRoot is utility which provides full immutability and atomicity to a Linux system, by transacting between two root filesystems. It's updates are performed using OCI images, to ensure that the system is always in a consistent state.
```

## SYNOPSIS

```md
abroot [command] [arguments] [options]
```

## DESCRIPTION

```md
ABRoot provides full immutability and atomicity by performing transactions between 2 root partitions (A<->B)

Usage:
  abroot [command]

Available Commands:
  completion  Generate the autocompletion script for the specified shell
  help        Help about any command
  kargs       Manage kernel parameters
  pkg         Manage packages
  rollback    Return the system to a previous state
  status      Display status
  upgrade     Update the boot partition

Flags:
  -h, --help      help for abroot
  -v, --verbose   Show more detailed output
      --version   version for abroot

Use "abroot [command] --help" for more information about a command.
```

## COMPLETION

```md
Generate the autocompletion script for abroot for the specified shell.
See each sub-command's help for details on how to use the generated script.

Usage:
  abroot completion [command]

Available Commands:
  bash        Generate the autocompletion script for bash
  fish        Generate the autocompletion script for fish
  powershell  Generate the autocompletion script for powershell
  zsh         Generate the autocompletion script for zsh

Flags:
  -h, --help   help for completion

Global Flags:
  -v, --verbose   show more detailed output

Use "abroot completion [command] --help" for more information about a command.
```

## KARGS

```md
Manage kernel parameters.

Usage:
  abroot kargs edit|show [flags]

Examples:
abroot kargs edit

Flags:
  -h, --help   help for kargs

Global Flags:
  -v, --verbose   Show more detailed output
```

## PKG

```md
Install and manage packages.

Usage:
  abroot pkg add|remove|list|apply [flags]

Examples:
abroot pkg add <pkg>

Flags:
  -h, --help   help for pkg

Global Flags:
  -v, --verbose   Show more detailed output
```

## ROLLBACK

```md
Executes a system rollback, discarding changes made to the present root.

Usage:
  abroot rollback [flags]

Examples:
abroot rollback

Flags:
  -h, --help   help for rollback

Global Flags:
  -v, --verbose   Show more detailed output
```

## STATUS

```md
Display the current ABRoot status.

Usage:
  abroot status [flags]

Examples:
abroot status

Flags:
  -d, --dump   Dump the ABRoot status to an archive
  -h, --help   help for status
  -j, --json   Show output in JSON format

Global Flags:
  -v, --verbose   Show more detailed output
```

## UPGRADE

```md
Update the boot partition for maintenance purposes (for advanced users only)

Usage:
  abroot upgrade [flags]

Examples:
abroot upgrade

Flags:
  -c, --check-only   check for updates but do not apply them
  -f, --force        force update the boot partition without asking for confirmation
  -h, --help         help for upgrade

Global Flags:
  -v, --verbose   Show more detailed output
```

## SEE ALSO

- [`apx`](apx)
- [`vso`](vso)

## REPORTING BUGS

Report bugs to the [issue tracker](https://github.com/Vanilla-OS/ABRoot/issues).
