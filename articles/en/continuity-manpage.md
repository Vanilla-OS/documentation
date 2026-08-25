---
Title: Continuity Manpage
Description: Command reference for Continuity 1.0.
PublicationDate: 2026-08-24
Listed: true
Authors:
  - Vanilla-OS
Tags:
  - continuity
  - manpage
---

## Synopsis

```text
continuity [command] [options]
```

Continuity commands that read or change system backups require administrative
privileges on Vanilla OS. Run them as `host-shell pkexec continuity ...` from
the default terminal.

## Commands

### `backup`

Create a snapshot with an optional label.

```text
continuity backup [LABEL] [--dry-run]
```

### `list`

List saved snapshots.

```text
continuity list [--details]
```

### `inspect`

Show the metadata and provider contents of one snapshot.

```text
continuity inspect SNAPSHOT_ID
```

### `restore`

Restore one snapshot.

```text
continuity restore SNAPSHOT_ID [--dry-run]
```

### `prune`

Delete snapshots outside the selected retention count.

```text
continuity prune [--keep-last NUMBER] [--dry-run]
```

The default value for `--keep-last` is 7.

### `status`

Show repository and operation status.

```text
continuity status
```

### `device`

Manage external block devices used as repositories.

```text
continuity device list [--all]
continuity device init DEVICE [options]
continuity device unlock DEVICE
continuity device lock [DEVICE]
continuity device info [DEVICE]
```

`device init` destroys data on the selected device. Its options include:

- `--label`: set the filesystem label.
- `--fs`: select `ext4` or `btrfs`.
- `--no-encrypt`: create an unencrypted repository.
- `--force`: skip safety confirmation.
- `--password`: provide a LUKS2 password.
- `--no-activate`: do not activate the repository after initialization.

### `daemon`

Start the D-Bus service used by desktop integrations.

```text
continuity daemon
```

### `version`

Show version information.

```text
continuity version
```

### `man`

Generate the local manual page.

```text
continuity man
```

Run `continuity COMMAND --help` for the exact options accepted by the installed
version.

## Reporting bugs

Report bugs in the [Continuity issue tracker](https://github.com/Vanilla-OS/continuity/issues).
