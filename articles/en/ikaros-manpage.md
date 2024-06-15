---
Title: Ikaros Manpage
Description: Manpage for the Ikaros utility.
PublicationDate: 2023-09-03
Authors: 
  - Vanilla-OS
Tags:
  - ikaros
  - manpage
---

## NAME

```md
Ikaros is a command line tool for managing drivers for your devices.
```

## SYNOPSIS

```md
ikaros [command] [arguments] [options]
```

## DESCRIPTION

```md
Ikaros is a command line tool for managing drivers for your devices

Usage:
  ikaros [command]

Available Commands:
  auto-install Auto install correct drivers
  completion   Generate the autocompletion script for the specified shell
  help         Help about any command
  install      Install a driver
  list-devices List devices

Flags:
  -h, --help      help for ikaros
  -v, --version   version for ikaros

Use "ikaros [command] --help" for more information about a command.
```

## AUTO-INSTALL

```md
Auto install the correct drivers for all devices

Usage:
  ikaros auto-install [flags]

Examples:
ikaros auto-install

Flags:
  -h, --help   help for auto-install
```

## COMPLETION

```md
Generate the autocompletion script for ikaros for the specified shell.
See each sub-command's help for details on how to use the generated script.

Usage:
  ikaros completion [command]

Available Commands:
  bash        Generate the autocompletion script for bash
  fish        Generate the autocompletion script for fish
  powershell  Generate the autocompletion script for powershell
  zsh         Generate the autocompletion script for zsh

Flags:
  -h, --help   help for completion

Use "ikaros completion [command] --help" for more information about a command.
```

## INSTALL

```md
Install a driver

Usage:
  ikaros install [flags]

Examples:
ikaros install

Flags:
  -h, --help   help for install
```

## LIST-DEVICES

```md
List all devices

Usage:
  ikaros list-devices [flags]

Examples:
ikaros list-devices

Flags:
  -h, --help   help for list-devices
  -j, --json   Output as JSON
```

## SEE ALSO

- [`abroot`](abroot)
- [`apx`](apx)
- [`vso`](vso)

## REPORTING BUGS

Report bugs to the [issue tracker](https://github.com/Vanilla-OS/Ikaros/issues).
