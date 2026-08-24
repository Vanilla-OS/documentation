---
Title: Apx - Introduction
Description: Install development tools and applications in managed subsystems.
PublicationDate: 2026-08-24
Listed: true
Authors:
  - Vanilla-OS
Tags:
  - apx
  - packages
  - subsystems
---

Apx installs packages in managed containers called subsystems. Packages can use
your display, audio, devices, and files without changing the Vanilla OS system
image.

Use Flatpak for most desktop applications. Use Apx when you need a package from
a traditional distribution repository, a development environment, or an
isolated command-line tool. Use ABRoot only for software that must be installed
in the host image.

## Stacks and subsystems

A stack defines a container image and its package manager. A subsystem is a
container created from a stack. Vanilla OS includes stacks based on Debian and
openSUSE Leap, and administrators can add custom stacks.

List the available stacks and subsystems:

```bash
apx stacks list
apx subsystems list
```

Create a subsystem:

```bash
apx subsystems new --name dev --stack vanilla-dev
```

The `--home` option assigns a separate home directory. The `--init` option runs
systemd inside the subsystem.

## Package operations

Each subsystem name becomes an Apx command. For a subsystem named `dev`:

```bash
apx dev update
apx dev install git gcc
apx dev search ripgrep
apx dev list
apx dev remove gcc
apx dev upgrade
```

Enter its shell or run one command without entering it:

```bash
apx dev enter
apx dev run git --version
```

## Desktop integration

Export a desktop application or command to the host:

```bash
apx dev export --app APP_NAME
apx dev export --bin COMMAND
```

Remove an export with the matching `unexport` command. Apx 3 uses `--app` in
place of the former `--app-name` option.

## Configuration

Apx 3 stores its main configuration in `config.json`. Configurations made for
older releases may use `apx.json` and must be updated before reuse.

## Usage

- [Apx manpage](apx-manpage)
- [Vanilla System Operator](vso)
- [ABRoot](abroot)
