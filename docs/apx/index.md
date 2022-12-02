---
title: Package Manager (apx) - Vanilla OS
description: Find out how to use apx, the Vanilla OS package manager.
---

# Package Manager (`apx`)

`apx` is the Vanilla OS package manager. It's meant to be easy to use, but 
also powerful with support for installing packages from multiple sources without 
altering the root filesystem.

## How it works

`apx` introduces a whole new paradigm in package management. The idea is to use 
your system only as a box for storing your files, leaving it clean of packages 
and limiting the risk of breaking due to incompatible, poorly constructed or 
conflicting packages.

This is done by installing software inside one or more "managed" containers, 
which are fully managed by `apx` and have restricted access to your system's 
resources, while still being able to use the same drivers, display server, etc.

Your home directory is mapped inside the container, so you can access your 
configuration files, preferences and other vital data needed by the installed 
packages, as well as being able to access your own files from the installed 
software, e.g. by opening a file in LibreOffice.

### Host system

While installing software on the host is against the ideology of the project, 
there are cases where this cannot be avoided, for example when you need to 
install a kernel module.

In cases like this, you can use the command `abroot exec apt install *package name*`
to bypass the container and install directly on the host, *but be aware that this 
is not recommended*.

### Multiple sources

By default, `apx` provides a container based on your Linux distribution (Ubuntu 
22.10 for Vanilla OS 22.10) and wraps all commands from the distribution's 
package manager (`apt` for Ubuntu).

Nevertheless, it is still possible to install packages from other distributions 
using other package managers, for example, using the `--aur` flag, a second 
container based on Arch Linux will be created. Here, `apx` will manage software 
from the AUR (and Pacman), always integrating it with the host system.

For quality control and testing needs, we have chosen to limit this feature 
to specific implementations. Currently, only the `--aur` flag is supported, but 
we are planning to implement support for the Nix package manager as well.

### The name

The name `apx` comes from **apt (Advanced Packaging Tool)**, the package 
manager used by Debian and its derivatives, and **X**, which should be seen as 
2 lines (host and container) overlapping, where the container is on top, meaning 
it is on top of the host system.

## Usage

- [Manpage](/docs/apx/manpage)
