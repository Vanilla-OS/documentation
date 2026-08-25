---
Title: Continuity - Introduction
Description: Back up and restore Vanilla OS user data and system metadata.
PublicationDate: 2026-08-24
Listed: true
Authors:
  - Vanilla-OS
Tags:
  - continuity
  - backup
  - restore
---

Continuity creates snapshot-based backups for Vanilla OS. A snapshot can
include user home directories, the list of installed Flatpak applications, and
ABRoot metadata.

Continuity 1.0 is included with Vanilla OS 3 Reunion.

## Create a backup

Run Continuity on the host with administrative privileges:

```bash
host-shell pkexec continuity backup
```

An optional label helps identify the snapshot later:

```bash
host-shell pkexec continuity backup before-testing-drivers
```

Use `--dry-run` to preview the files and providers involved without storing a
snapshot.

## List and inspect snapshots

```bash
host-shell pkexec continuity list
host-shell pkexec continuity list --details
host-shell pkexec continuity inspect SNAPSHOT_ID
```

The detailed view reports the stored providers, size, timestamp, and label.

## Restore a snapshot

Preview a restore before applying it:

```bash
host-shell pkexec continuity restore SNAPSHOT_ID --dry-run
```

Restore it after reviewing the preview:

```bash
host-shell pkexec continuity restore SNAPSHOT_ID
```

The user-data provider restores home directories, the Flatpak provider
reinstalls recorded applications, and the ABRoot provider restores the saved
ABRoot metadata.

## Retention

Continuity keeps the seven newest snapshots by default. Remove older snapshots
manually with:

```bash
host-shell pkexec continuity prune --keep-last 7
```

Add `--dry-run` to preview the snapshots that would be removed.

## Repository locations

The default repository is `/var/lib/vanilla-continuity/repo`. Continuity also
supports:

- an external block device, optionally encrypted with LUKS2;
- SFTP and FTP storage;
- NFS shares.

The configuration format also supports SMB. Vanilla OS 3 does not include the
required `cifs-utils` host package by default, so SMB repositories need a
custom image or an ABRoot host package change.

List candidate devices before selecting one:

```bash
host-shell pkexec continuity device list
```

`continuity device init` formats the selected device and destroys its existing
data. Check its path with `device list` and read `device init --help` before
running it.

Unlock an initialized repository, inspect it, then lock it when finished:

```bash
host-shell pkexec continuity device unlock DEVICE
host-shell pkexec continuity device info DEVICE
host-shell pkexec continuity device lock DEVICE
```

## Configuration

System-wide settings are read from `/usr/share/continuity/config.json` and can
be overridden in `/etc/continuity/config.json`. User and development overrides
are also supported by the Vanilla OS SDK configuration loader.

```json
{
  "repository_path": "/var/lib/vanilla-continuity/repo",
  "default_deduplicate": false,
  "max_parallel_workers": 2,
  "retention_keep_last": 7,
  "exclude_patterns": [
    ".cache",
    ".local/share/Trash",
    "node_modules",
    ".tmp",
    "*.tmp"
  ],
  "enabled_providers": [
    "userdata",
    "flatpak",
    "abroot"
  ]
}
```

Remote repositories use the optional `remote` object. Supported types are
`sftp`, `ftp`, `smb`, and `nfs`; their fields depend on the selected protocol.
Do not store a remote password in a world-readable configuration file. Prefer
an SFTP key file where possible.

## Usage

- [Continuity manpage](continuity-manpage)
- [ABRoot](abroot)
