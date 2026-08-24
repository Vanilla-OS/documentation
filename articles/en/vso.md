---
Title: Vanilla System Operator - Introduction
Description: Manage upgrades, native packages, and scheduled tasks with VSO.
PublicationDate: 2026-08-24
Listed: true
Authors:
  - Vanilla-OS
Tags:
  - vso
  - maintenance
  - packages
  - automation
  - updates
---

Vanilla System Operator, or VSO, provides the user-facing commands for system
upgrades, native package management, and scheduled tasks in Vanilla OS.

## System upgrades

Check for a new Vanilla OS image:

```bash
vso upgrade check
```

Prepare the available upgrade in the background:

```bash
vso upgrade
```

Pass `--now` to reboot after the upgrade is ready:

```bash
vso upgrade --now
```

VSO delegates image deployment to ABRoot. The current system remains usable
while the future state is prepared.

## Native subsystem

The native subsystem installs Debian packages without changing the host image.
Initialize it before first use:

```bash
vso native init
```

Install packages, enter its shell, or run a command directly:

```bash
vso native install PACKAGE
vso native shell
vso native run COMMAND
```

Export a graphical application or command to the desktop:

```bash
vso native export --app APP_NAME
vso native export --bin COMMAND
```

Apx manages the native subsystem under the name `apx-vso-native`. Installations
upgraded from an older release may also contain the legacy `apx-vso-pico`
subsystem.

VSO 3 no longer provides the former Android and Waydroid commands.

## Scheduled tasks

VSO can run user commands on a schedule. List the tasks already configured:

```bash
vso tasks list
```

Use `vso tasks new --help` to view the scheduling fields accepted by the
installed version. Tasks can be removed or rotated with `vso tasks rm` and
`vso tasks rotate`.

## Configuration

Read and change a VSO setting with positional arguments:

```bash
vso config get KEY
sudo vso config set KEY VALUE
vso config show
```

VSO 3 replaces the former `vso config set -k KEY -v VALUE` syntax. Changing the
system configuration requires administrative privileges.
The current settings are `updates.smart`, which accepts `true` or `false`, and
`updates.schedule`, which accepts `never`, `daily`, `weekly`, or `monthly`.

## Usage

- [VSO manpage](vso-manpage)
- [ABRoot](abroot)
- [Apx](apx)
