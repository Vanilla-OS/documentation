---
title: Immutability (almost) - Vanilla OS
description: Find out how to use Almost, the on-demand immutability utility.
---

# Immutability (`almost`)
`almost` is a utility that provides on-demand immutability by toggling the
immutability of files and directories in the system root. It also provides
a way to create layers on top of immutable directories, allowing you to test
changes before committing them.

## How it works
Immutability in `almost` is obtained by setting the `i` flag on all files and
directories in the system root, except those that are used to store software
configuration files and the user's home directory (`/home, /etc, /var`).

The same can be achieved using the `chattr` command, but `almost` provides
consistency by restoring the default state of the system after a reboot, and
with additional features to better manage immutability, e.g. launching a command while
temporarily disabling immutability.

### On-demand immutability
This is called *on-demand* immutability as it can be enabled or disabled
at any time. Immutability is meant to be used as a safety measure to prevent
accidental changes to the system, so it should be kept enabled most of the
time.

Due to its nature, `almost` is ready to use and works on all filesystems
and configurations.

### The name
The name `almost` comes from the fact that it is not a full-fledged
immutability solution, but rather a tool to help you achieve it, while still being
able to make changes when needed.

## What it is not
`almost` has no support for snapshots. Every change made to the system is
permanent and cannot be reverted without restoring from a backup or dowgrading
the system. To avoid this, you should always test your changes using layers
before committing them. The only way to disable immutability is to edit
a configuration file which is not in the common directories, or to install
drivers. Disabling the immutability to install an application or library is
not recommended. Use [`apx`](/docs/apx), [`Flatpak`](/docs/flatpak),
[`Snap`](/docs/snap) or [`AppImage`](/docs/appimage) instead.

## Usage
- [Manpage](/docs/almost/manpage)
- [Layers](/docs/almost/layers)
- [Configuration](/docs/almost/configuration)
