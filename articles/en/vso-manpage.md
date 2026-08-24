---
Title: VSO Manpage
Description: Command reference for Vanilla System Operator 3.
PublicationDate: 2026-08-24
Listed: true
Authors:
  - Vanilla-OS
Tags:
  - vso
  - manpage
---

## Synopsis

```text
vso [command] [options]
```

## Commands

### `config`

Read or change system configuration.

```text
vso config get KEY
vso config set KEY VALUE
vso config show
```

### `native`

Manage the VSO package subsystem.

```text
vso native init [--force]
vso native install PACKAGE...
vso native remove PACKAGE...
vso native run COMMAND [arguments]
vso native shell
vso native sideload FILE.deb
vso native update
vso native upgrade
vso native export --app APP_NAME
vso native export --bin COMMAND [--bin-output PATH]
vso native unexport --app APP_NAME
vso native unexport --bin COMMAND [--bin-output PATH]
```

`vso native run --no-reset` keeps the subsystem state after the command exits.

### `tasks`

Create and manage scheduled commands.

```text
vso tasks list
vso tasks new [options]
vso tasks rm [options]
vso tasks rotate
```

Run `vso tasks new --help` for the scheduling options and
`vso tasks rm --help` for task selection options.

### `upgrade`

Check for or apply a system image update.

```text
vso upgrade check [--json]
vso upgrade [--now]
```

`--now` reboots after the new state is ready. Without it, the new state is used
at the next reboot.

### `man`

Generate the local manual page.

```text
vso man
```

## Global options

- `--help`, `-h`: show help.
- `--version`, `-v`: show the version.

Run `vso COMMAND --help` for command-specific flags.

## Migration from VSO 2

The main command changes are:

| VSO 2 | VSO 3 |
| --- | --- |
| `vso sys-upgrade check` | `vso upgrade check` |
| `vso sys-upgrade upgrade` | `vso upgrade` |
| `vso pico-init` | `vso native init` |
| `vso install PACKAGE` | `vso native install PACKAGE` |
| `vso export --app-name APP` | `vso native export --app APP` |
| `vso config set -k KEY -v VALUE` | `vso config set KEY VALUE` |

Android and Waydroid management commands were removed in VSO 3.

## Reporting bugs

Report bugs in the [VSO issue tracker](https://github.com/Vanilla-OS/vanilla-system-operator/issues).
