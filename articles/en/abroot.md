---
Title: ABRoot - Introduction
Description: Learn how ABRoot provides atomic, image-based system updates.
PublicationDate: 2026-08-24
Listed: true
Authors:
  - Vanilla-OS
Tags:
  - abroot
  - updates
  - immutability
---

ABRoot provides atomic system updates for Vanilla OS. It deploys complete OCI
images instead of changing the running root filesystem one package at a time.

## How it works

Vanilla OS keeps two system states: the current state and a future state. An
upgrade is prepared in the future state while you continue to use the current
one. After the operation succeeds, a reboot activates the new state. The
previous state stays available for rollback.

This design keeps the deployed system image consistent and prevents an
interrupted upgrade from leaving a partially updated root filesystem.

## System upgrades

Check whether an image is available:

```bash
sudo abroot upgrade --check-only
```

Download and prepare the latest image:

```bash
sudo abroot upgrade
```

Reboot to enter the new state. Vanilla System Operator provides the usual
user-facing commands for the same workflow:

```bash
vso upgrade check
vso upgrade
```

## Rollback

Check whether rollback is available, then select the previous state:

```bash
sudo abroot rollback --check-only
sudo abroot rollback
```

Reboot to complete the rollback.

## Host packages

Use ABRoot packages only for software that must be part of the host system,
such as drivers or kernel modules. Applications should normally be installed
with Flatpak, Apx, or the VSO native subsystem.

```bash
sudo abroot pkg add PACKAGE
sudo abroot pkg apply
```

Package changes are applied to a newly built system state and require a
reboot. Review the pending package list with `sudo abroot pkg list`.

## Rebase

Rebase changes the OCI image used by the installation:

```bash
sudo abroot rebase IMAGE_NAME
```

Use `--dry-run` to inspect the operation first. Rebase only to images made for
ABRoot and your system architecture.

## Kernel arguments

Edit persistent kernel arguments with:

```bash
sudo abroot kargs edit
```

The command opens the configuration in `$EDITOR`. Invalid kernel arguments can
prevent a state from booting, so keep the previous state available until the
new one has been tested.

## Persistent paths

Runtime and user data live outside the replaced system image. In Vanilla OS 3,
`/opt` and `/usr/local` are persistent paths backed by `/var`. Custom images
must not replace those paths with image-owned directories or files.

## Usage

- [ABRoot manpage](abroot-manpage)
- [Integrating ABRoot](abroot-porting)
- [Apx](apx)
- [Vanilla System Operator](vso)
