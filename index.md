---
title: Vanilla OS Documentation
description: Find out how to use Vanilla OS and all its tools and settings.
---

# Vanilla OS
Taste the GNOME Vanilla experience on Ubuntu with some spice.

## FAQ
Answers to the most frequently asked questions (even though the project is very young).
- **Why a new Distribution?**\
  Vanilla OS arose out of the need for an Ubuntu-based Linux distribution that 
  would provide vanilla GNOME without any changes to the user 
  experience. Later, its scope was extended to experiment with some tools and 
  technologies, such as Almost (on-demand immutability) and Apx (the 
  Distrobox-based subsystem).
- **Does it use OSTree?**\
  No. Vanilla OS achieves immutability through [`almost`](https://github.com/Vanilla-OS/almost). 
  We wrote this utility for On-Demand Immutability based on the 
  immutability attribute of files. This approach works on any partition 
  schema/file system. OSTree may still be considered in the future.
- **Rolling Release?**\
  No. Vanilla OS is a point release and follows the Ubuntu release cycle.

## Sections
- **[Immutability (`almost`)](/docs/almost)**\
Almost is a utility for on-demand immutability based
on the immutability attribute of files.

- **[Package Manager (`apx`)](/docs/apx)**\
Apx is a package manager that allows you to install and manage packages in a
managed container, without affecting the host system. Occasionally, it is
possible to use `apx` to install packages on the host system as well.

- **[Installation](/docs/installation)**\
Learn how to install Vanilla OS to your device.