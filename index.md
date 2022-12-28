---
title: Vanilla OS Documentation
description: Find out how to use Vanilla OS and all its tools and settings.
---

# Vanilla OS

Taste the GNOME Vanilla experience on Ubuntu with some spice.

**This page is the official documentation for Vanilla OS components.**\
Check out [**Handbook**](https://handbook.vanillaos.org) for user-written guides and tutorials.

## FAQ

Answers to the most frequently asked questions about Vanilla OS.

- **Why a new Distribution?**\
  Vanilla OS arose out of the need for an Ubuntu-based Linux distribution that 
  would provide vanilla GNOME without any changes to the user 
  experience. Later, its scope got extended to experiment with some tools and 
  technologies, such as ABRoot and Apx (the 
  Distrobox-based subsystem).
  
- **Does it use OSTree?**\
  No. Vanilla OS achieves immutability through [`ABRoot`](https://github.com/Vanilla-OS/ABRoot) [previously achieved through `almost`]. Usage of OSTree may be considered in the future.
 
  We wrote `almost` utility for On-Demand Immutability based on the 
  immutability attribute of files. This approach worked on any partition 
  schema/file system.
  
  We introduced a new utility [ABRoot](https://github.com/Vanilla-OS/ABRoot) replacing the `almost` utility to provide full immutability and atomicity, by transacting between 2 root partitions (A⟺B). It also allows on-demand transactions via a transactional shell.
  
- **Rolling Release?**\
  No. Vanilla OS is a point release and follows the Ubuntu release cycle.

## User Guides

- **[Installation](https://handbook.vanillaos.org/2022/11/05/installation.html)**
- **[First Setup](https://handbook.vanillaos.org/2022/11/18/first-setup.html)**
- **[Updates](https://handbook.vanillaos.org/2022/12/10/updates.html)**
- **[More guides](https://handbook.vanillaos.org/)**

## Core Components Documentation

- **[Apx](/docs/apx)**\
  is container based package manager which allows installing packages from other distributions in a sandboxed environment.

- **[ABRoot](/docs/ABRoot)**\
  is a utility that allow fully atomic transactions between 2 root partitions (A⟺B).

- **[VSO](/docs/vso)**\
  is an utility which allows you to perform maintenance tasks on your Vanilla OS installation.

- ~~**[Almost](/docs/almost)**~~\
  ~~allows you to make your system immutable by simply toggling the i attribute of files.~~
