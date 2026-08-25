---
Title: ABRoot Manpage
Description: Command reference for ABRoot 2.6.
PublicationDate: 2026-08-24
Listed: true
Authors:
  - Vanilla-OS
Tags:
  - abroot
  - manpage
---

## Synopsis

```text
abroot [command] [options]
```

ABRoot manages atomic OCI-based system states.

## Commands

### `config-editor`

Open the ABRoot configuration in the default command-line editor.

```bash
abroot config-editor
```

### `kargs`

Show or edit persistent kernel arguments.

```text
abroot kargs edit|show
```

### `pkg`

Manage packages included in the host system.

```text
abroot pkg add|remove|list|apply [options]
```

Options include:

- `--dry-run`, `-d`: preview the operation.
- `--force-enable-user-agreement`, `-f`: accept the package agreement for an embedded system.
- `--force-apply`: apply the package operation even when no changes are detected.
- `--delete-old-system`: delete the previous system after applying changes.

### `rebase`

Change the OCI image used for future system states.

```text
abroot rebase IMAGE_NAME [options]
```

Options include:

- `--dry-run`, `-d`: preview the rebase.
- `--remove-packages`, `-r`: remove configured host packages.
- `--keep-packages`, `-k`: keep configured host packages.
- `--rebase-only`, `-n`: change the image without starting an upgrade.

### `rollback`

Select the previous system state for the next boot.

```text
abroot rollback [--check-only]
```

### `status`

Show the current and future system states.

```text
abroot status [--json] [--dump]
```

`--json`, `-j` prints JSON. `--dump`, `-d` creates a diagnostic archive.

### `update-initramfs`

Rebuild the initramfs in the future system state.

```text
abroot update-initramfs [--dry-run] [--delete-old-system]
```

### `upgrade`

Check for, download, and prepare a new system image.

```text
abroot upgrade [options]
```

Options include:

- `--check-only`, `-c`: check without applying an update.
- `--dry-run`, `-d`: preview the operation.
- `--force`, `-f`: run even when the system is current.
- `--delete-old-system`: remove the previous system after the upgrade.
- `--cancel`: cancel the current upgrade.
- `--unblock`: clear an upgrade block.

### `completion`

Generate completion scripts for Bash, Fish, PowerShell, or Zsh.

```text
abroot completion bash|fish|powershell|zsh
```

## Global options

- `--help`, `-h`: show help.
- `--verbose`, `-V`: show detailed output.
- `--version`, `-v`: show the version.

Run `abroot COMMAND --help` for the flags accepted by an installed version.

## Reporting bugs

Report bugs in the [ABRoot issue tracker](https://github.com/Vanilla-OS/ABRoot/issues).
