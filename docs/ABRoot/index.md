---
title: Immutability (ABRoot) - Vanilla OS
description: Utility proving full immutability and atomicity by transacting between 2 root partitions with support for on-demand transactions via a transactional shell in Vanilla OS.
---

# Immutability (`abroot`)

`abroot` is a utility that provides complete immutability and atomicity by transacting between 2 root partitions (A⟺B), it also allows on-demand transactions via a transactional shell.

## How it works

Linux file system is a hierarchical file structure containing root and other directories. 
The root is the primary hierarchical directory containing other partitions.
In immutable file systems, the root partition is read-only, preventing the installation of essential packages, firmware and drivers on the host.

`abroot` allows you to install kernel modules, drivers and other essential packages on the host without compromising the filesystems immutability. 

When a command gets executed in `abroot` a transaction is started in the transaction shell in the second root partition. If the transaction succeeds, the changes are applied using an overlay and synced with the current root upon reboot. If the transaction fails, no changes are applied (due to a property known as atomicity). `abroot` also allows on-demand transactions using the `abroot shell` command.

Vanilla OS installations contain two root and boot partitions for the two states (A- 20GB & B- 20GB) as it is a requirement for `abroot`.

## States

`abroot` has two states - present and future. When you are first into your Vanilla OS installation the present state is A. When you reboot your system, the state will automatically switch to B. When you install a package using `abroot`,  it gets installed in the future root partition synced with the current root partition upon reboot.

## Updates

`abroot` powers the `vso` utility allowing us to do automatic smart updates and installation of updates in the background in the future root partition, thus saving time as an offline update during reboot isn't required.

## Naming

ABRoot's name is a pure reference to the two transacting root partitions A and B (A⟺B).

## Usage

- [Manpage](/docs/ABRoot/manpage)
