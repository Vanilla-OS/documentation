---
title: Package Manager (apx) - Vanilla OS
description: Find out how to use apx, the Vanilla OS package manager.
---

# Package Manager (`apx`)
`apx` is the Vanilla OS package manager. It's meant to be simple to use, but
also powerful with support to installing packages from multiple sources without 
altering the root filesystem.

## How it works
This package manager introduces a whole new paradigm in package management. The 
idea is to use your system only as a box where the user can store all their 
files, leaving it clean of packages while limiting the risk of breaking due 
to incompatible, poorly constructed or conflicting packages.

This is done by installing software inside one or more "managed" containers,
which are fully managed by `apx` and has restricted access to your system's
resources being still able to use the same drivers, display server, etc.

The user home directory is mapped inside the container, so you can access your
configuration files, preferences and other vital data needed by the installed
packages, as well as being able to access your own files from the installed
software, e.g. by opening a file in LibreOffice.

### Host system
While installing software on the host is against the project ideology, there 
are cases where this cannot be prevented, for example when you need to install 
a kernel module. 

In these cases, you would use the `--sys` flag to bypass the container and 
install directly on the host, *but be aware that this is not recommended*. `apx` 
works with [`almost`](/docs/almost) to temporary disable the immutability, 
letting you install the needed packages while restoring the system afterwards.

### Multiple sources
Apx by default provides a container based on your Linux distribution (Ubuntu 
22.10 for Vanilla OS 22.10) and wraps all commands from the distribution's 
package manager (`apt` for Ubuntu). 

Nevertheless it is still possible to install packages from other distributions 
using other package managers, for example using the `--aur` flag a second 
container based on Arch Linux will be created, where apx will manage software 
from AUR (and Pacman) always integrating it with the host system. 

For quality issues and testing needs, we have chosen to limit this feature 
to specific implementations. Currently only `--aur` is supported, we are 
planning to implement support for the Nix package manager as well.

### The name
The name `apx` comes from **Apt (Advanced Packaging Tool)**, the package 
manager used by Debian and its derivatives, and **X**, which must be seen as 
2 lines (host and container) that overlap, where container is always on top 
meaning it is always on top of the system.

## Usage
- [Manpage](/docs/apx/manpage)
