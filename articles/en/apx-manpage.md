---
Title: Apx Manpage
Description: Command reference for Apx 3.
PublicationDate: 2026-08-24
Listed: true
Authors:
  - Vanilla-OS
Tags:
  - apx
  - manpage
---

## Synopsis

```text
apx [command] [options]
apx SUBSYSTEM [command] [options]
```

## Resource commands

Apx manages package-manager definitions, stacks, and subsystems. The three
resource groups use the same management pattern where applicable:

```text
apx pkgmanagers list|show|new|update|rm|import|export
apx stacks list|show|new|update|rm|import|export
apx subsystems list|new|reset|rm
```

Common options include:

- `--name`, `-n`: select or name a resource.
- `--force`, `-f`: skip removal confirmation.
- `--json`, `-j`: print list output as JSON.
- `--input`, `-i`: read an imported definition.
- `--output`, `-o`: write an exported definition.
- `--no-prompt`, `-y`: use defaults without prompting.

### Create a subsystem

```text
apx subsystems new --name NAME --stack STACK [--home PATH] [--init]
```

- `--name`, `-n`: set the subsystem name.
- `--stack`, `-s`: select the stack.
- `--home`, `-H`: use a custom home directory.
- `--init`, `-i`: run systemd inside the subsystem.

### Create a stack

```text
apx stacks new --name NAME --base IMAGE --pkg-manager NAME [options]
```

`--packages`, `-p` adds packages to the stack definition.

## Subsystem commands

Replace `SUBSYSTEM` with a name shown by `apx subsystems list`.

```text
apx SUBSYSTEM enter
apx SUBSYSTEM run COMMAND [arguments]
apx SUBSYSTEM install PACKAGE...
apx SUBSYSTEM remove PACKAGE...
apx SUBSYSTEM update
apx SUBSYSTEM upgrade
apx SUBSYSTEM list
apx SUBSYSTEM search QUERY
apx SUBSYSTEM show PACKAGE
apx SUBSYSTEM export --app APP_NAME
apx SUBSYSTEM export --bin COMMAND
apx SUBSYSTEM unexport --app APP_NAME
apx SUBSYSTEM unexport --bin COMMAND
apx SUBSYSTEM start
apx SUBSYSTEM stop
apx SUBSYSTEM autoremove
apx SUBSYSTEM clean
apx SUBSYSTEM purge PACKAGE...
```

`install --no-export`, or `-n`, skips automatic desktop entry export.
`export` and `unexport` also accept `--bin-output`, or `-o`, for a custom
binary export directory.

Use `apx COMMAND --help` or `apx SUBSYSTEM COMMAND --help` for flags supported
by the installed stack and package manager.

## Other commands

```text
apx man
```

`apx man` generates the local manual page. `apx --version` prints the installed
version.

## Reporting bugs

Report bugs in the [Apx issue tracker](https://github.com/Vanilla-OS/apx/issues).
