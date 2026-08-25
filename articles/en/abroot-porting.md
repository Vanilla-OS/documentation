---
Title: Integrating ABRoot
Description: Requirements for integrating ABRoot 2 with a distribution or image.
PublicationDate: 2026-08-24
Listed: true
Authors:
  - Vanilla-OS
Tags:
  - abroot
  - porting
  - images
---

ABRoot 2 deploys complete OCI images. It cannot be added to an existing system
by installing the binary alone: the boot process, disk layout, image recipe,
configuration, and update service must agree on the same A/B model.

Use the [Vanilla OS image recipes](https://github.com/Vanilla-OS) as the
reference implementation and test changes in a virtual machine with snapshots.

## Integration requirements

An integration needs:

- two compatible system states and a bootloader able to select either state;
- an OCI image built for the target architecture;
- ABRoot configuration in `/etc/abroot`;
- initramfs hooks and services required to prepare and activate states;
- persistent mounts for user and runtime data;
- an update source that publishes compatible image metadata.

ABRoot 2 does not provide the ABRoot 1 transactional shell, overlay layout, or
transaction hook directories. Do not follow ABRoot 1 porting instructions for a
new image.

## Image filesystem rules

The system image owns the immutable operating system files. Store mutable data
on persistent mounts instead. Vanilla OS 3 maps `/opt` and `/usr/local` into
`/var`, so an image recipe must not place image-owned content at either path.

Put user data in `/home`, application state in the appropriate persistent
directory, and system configuration in the locations prepared by the image
recipe. Test upgrades with data already present to catch mount conflicts.

## Development workflow

Build and test the image recipe before testing ABRoot itself. In a disposable
VM, verify each of these operations:

1. Install and boot the first state.
2. Run `abroot status` and inspect both states.
3. Apply `abroot upgrade`, then boot the new state.
4. Run `abroot rollback`, then boot the previous state.
5. Add and remove a host package with `abroot pkg`.
6. Interrupt a test upgrade and confirm the current state still boots.

The ABRoot source and issue tracker are in the
[ABRoot repository](https://github.com/Vanilla-OS/ABRoot).
