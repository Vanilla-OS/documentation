---
title: Vanilla OS Documentation
description: Find out how to use Vanilla OS and all its tools and settings.
---

# Vanilla OS

Taste the GNOME Vanilla experience on Ubuntu with some spice.

**This page is the official documentation for Vanilla OS components.**\
Check out [Handbook](https://handbook.vanillaos.org) for user-written guides and tutorials.

## FAQ

Answers to the most frequently asked questions about Vanilla OS.

- **Why a new Distribution?**

  Vanilla OS arose out of the need for an Ubuntu-based Linux distribution that 
  would provide vanilla GNOME without any changes to the user 
  experience. Later, its scope got extended to experiment with some tools and 
  technologies, such as ABRoot and Apx (the 
  Distrobox-based subsystem).
  
- **Does it use OSTree?**

  No. Vanilla OS achieves immutability through [`ABRoot`](https://github.com/Vanilla-OS/ABRoot) [previously achieved through `almost`]. 
 
  We wrote `almost` utility for On-Demand Immutability based on the 
  immutability attribute of files. This approach worked on any partition 
  schema/file system. Usage of OSTree may be considered in the future.
  
  We introduced a new utility [ABRoot](https://github.com/Vanilla-OS/ABRoot) replacing `almost` utility to provide full immutability and atomicity, by transacting between 2 root partitions (A⟺B). It also allows on-demand transactions via a transactional shell.
  
- **Rolling Release?**

  No. Vanilla OS is a point release and follows the Ubuntu release cycle.

## Docs

- **[Installation](https://handbook.vanillaos.org/2022/11/05/installation.html)**

Documentation on how to install Vanilla OS using [Vanilla Installer](https://github.com/Vanilla-OS/vanilla-installer).

- **[First Setup](https://handbook.vanillaos.org/2022/11/18/first-setup.html)**

The Vanilla OS [First Setup](https://github.com/Vanilla-OS/first-setup) utility allows you to configure the system to your needs.

- **[Package Manager (`apx`)](/docs/apx)**

Apx is a package manager that allows you to install and manage packages in
managed containers without affecting the host system. `apx` supports installing packages from the Ubuntu Repository, Arch User Repository (AUR) and Fedora's DNF Repository inside a container. It is tightly-integrated with the host system. For GUI packages, a desktop file entry is created automatically and added to GNOME Application menu.

- **[Immutability (`abroot`)](/docs/ABRoot)**

ABRoot is a utility that provides full immutability and atomicity by transacting between 2 root partitions (A⟺B). It also allows on-demand transactions via a transactional shell.

- **[Vanilla Control Center](https://handbook.vanillaos.org/2022/12/10/install-additional-drivers.html)**

Vanilla Control Center is a graphical tool that allows you to configure the operating system,  [updates](https://handbook.vanillaos.org/2022/12/10/updates.html) and install additional drivers.

- **[Vanilla System Operator (`vso`)](/docs/VSO)**

[Vanilla System Operator](https://github.com/Vanilla-OS/vanilla-system-operator) is a utility for Vanilla OS which allows you to perform maintenance tasks such as updating your system, scheduling tasks, etc.

- **[Immutability (`almost`)](/docs/almost)**

~~[Almost](https://github.com/Vanilla-OS/almost) is a utility for on-demand immutability based
on the immutability attribute of files.~~ (Almost was replaced by `abroot`).
