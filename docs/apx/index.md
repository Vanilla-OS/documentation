---
title: Package Manager (apx)
description: Find out how to use apx, the Vanilla OS package manager.
sidebar_position: 1
---

# Package Manager (`apx`)

`apx` is the Vanilla OS package manager that is easy to use with support for installing packages from multiple sources inside containers without altering the root filesystem.

## How it works

`apx` introduces a whole new paradigm in package management. The idea is to use 
your system only as a box for storing your files, leaving it clean of packages 
and limiting the risk of breaking due to incompatible, poorly constructed or 
conflicting packages.

It gets done by installing software inside one or more containers fully managed by `apx` having restricted access to your system's resources while still being able to use the same drivers, display server, etc.

Your home directory is mapped inside the container so you can access your 
configuration files, preferences and other vital data needed by the installed 
packages, as well as being able to access your files from the installed 
software, e.g. by opening a file in LibreOffice.

### Host system

While installing software on the host is against the project's ideology, there are cases where it is essential. For example, when you need to 
install a kernel module or driver.

In cases like this, you can use the `abroot exec apt install <package_name>` or `abroot shell apt install <package_name>` command to bypass the container and install directly on the host, *but be aware that this 
is not recommended*.

### Multiple sources

By default, `apx` provides a container based on your Linux distribution (Ubuntu 
22.10 for Vanilla OS 22.10) and wraps all commands from the distribution's 
package manager (`apt` for Ubuntu).

Nevertheless, you can install packages from package other distributions. For example, using the `--aur` flag, a new
container based on Arch Linux will be created. Here, `apx` will manage the packages 
from the AUR (Pacman and yay), tightly integrating them with the host system. Using the `--dnf` flag with `apx` will create a new container based on Fedora Linux. Here, `apx` will manage packages from Fedora's DNF repository,  tightly integrating them with the host system. 

For GUI packages created inside `apx` containers,`.desktop` files are created automatically and added to the Applications menu. These applications are displayed beside other applications in the "Open with" menu in nautilus. GUI Packages installed inside containers gets shown in the Sub System section in the [Vanilla control center](https://github.com/Vanilla-OS/vanilla-control-center).

For quality control, we are limiting this feature to specific implementations. Currently, only `--aur` and `--dnf` flags are supported, but 
we are planning to implement support for the Nix package manager as well in future.

### Naming

The name `apx` comes from **apt (Advanced Packaging Tool)**, the package manager used by Debian and its derivatives. **X** consists of two lines (host and container) overlapping each other, where the container is on top, meaning 
it is on top of the host system.

## Usage

- [Manpage](/apx/manpage)
