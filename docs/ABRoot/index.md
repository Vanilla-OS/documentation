---
title: Immutability (ABRoot) - Vanilla OS
description: Find out how to use ABRoot.
---

# Immutability (`abroot`)

`abroot` is a utility that provides complete immutability and atomicity by making transactions between 2 root partitions (A⟺B), it also allows for on-demand transactions via a transactional shell.

## How it works

The Linux file system is a hierarchical file structure containing root and other directories. 
Root is the primary hierarchical directory containing all other partitions.
In immutable file systems, the root partition is read-only, preventing the installation of essential packages, such as drivers in the host.

`abroot` allows you to install kernel modules, drivers and other essential packages without compromising the filesystem's immutability. 

When a command gets executed in `abroot`, a transaction gets started in the transactional shell in the second root partition. If the transaction succeeds, the changes are applied using an overlay and synced with the current root on reboot. If the transaction fails, no changes are applied (due to a property known as atomicity). `abroot` also allows for on-demand transactions using the `abroot shell` command.

Vanilla OS installations create root and boot partitions for both states (20GB per root partition) as it is a requirement for `abroot`.

## States

`abroot` has two states - present and future. When you are in your Vanilla OS installation for the first time, the present state is A. When you reboot your system, the state automatically switches to B. When you install a package using `abroot`,  it gets installed in the future root partition and synced with the current root partition upon reboot.

## Updates

`abroot` powers the `vso` utility allowing for smart automatic updates and installation of updates in the background in the future root partition, thus saving time as an offline update during reboot isn't required.

## Naming

ABRoot's name refers to the two transacting root partitions A and B (A⟺B).

## Usage

- [Manpage](/docs/ABRoot/manpage)
