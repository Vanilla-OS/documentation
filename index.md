---
title: Vanilla OS Documentation
description: Find out how to use Vanilla OS and all its tools and settings.
---

# Vanilla OS

Taste the GNOME Vanilla experience on Ubuntu with some spice.

## FAQ

Answers to the most frequently asked questions (even though the project is very young).

- **Why a new Distribution?**

  Vanilla OS arose out of the need for an Ubuntu-based Linux distribution that 
  would provide vanilla GNOME without any changes to the user 
  experience. Later, its scope was extended to experiment with some tools and 
  technologies, such as ABRoot and Apx (the 
  Distrobox-based subsystem).
  
- **Does it use OSTree?**

  No. Vanilla OS achieves immutability through [`ABRoot`](https://github.com/Vanilla-OS/ABRoot) [previously achieved through `almost`]. 
 
  We wrote `almost` utility for On-Demand Immutability based on the 
  immutability attribute of files. This approach worked on any partition 
  schema/file system. Usage of OSTree may still be considered in the future.
  
  We introduced a new utility `abroot` replacing `almost` to provide full immutability and atomicity by transacting between 2 root partitions (A<->B), it also allows on-demand transactions via a transactional shell.
  
- **Rolling Release?**

  No. Vanilla OS is a point release and follows the Ubuntu release cycle.

## Sections

- **[Installation](/docs/installation)**

Documentation on how to install Vanilla OS using `vanilla-installer`.

- **[First Setup](/docs/first-setup)**

Vanilla OS first-setup wizard utility. Its purpose is to help the user to configure the system to their needs.

- **[Package Manager (`apx`)](/docs/apx)**

Apx is a package manager that allows you to install and manage packages in
managed containers without affecting the host system. `apx` supports installing packages (both CLI and GUI) from the Arch User Repository (AUR), Fedora's DNF Repository inside a container.

- **[Immutability (`abroot`)](/docs/ABRoot)**

ABRoot is an utility that provides full immutability and atomicity by transacting between 2 root partitions (A<->B), it also allows on-demand transactions via a transactional shell.

- **[Vanilla Control Center](/docs/vanilla-control-center)**

Vanilla OS Control Center is an utility to manage Vanilla OS components such as ABRoot, VSO, Apx. It supports installing drivers from `ubuntu-drivers-common`, has update options for VSO, GUI packages from `apx` containers are listed under the Sub System.

- **[Vanilla System Operator (`vso`)](/docs/VSO)**

Vanilla System Operator is an utility for Vanilla OS which allows you to perform maintenance tasks such as updating your system, scheduling tasks, etc.

- **[Immutability (`almost`)](/docs/almost)**

~~Almost is an utility for on-demand immutability based
on the immutability attribute of files.~~ (Almost was replaced by `abroot`).
