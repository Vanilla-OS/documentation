---
Title: Packaging
Description: Decide how software should be distributed for Vanilla OS.
PublicationDate: 2026-08-24
Listed: true
Authors:
  - Vanilla-OS
Tags:
  - packages
  - contributing
---

Vanilla OS deploys its host system as an OCI image. Choose the distribution
method based on how closely software must integrate with that host.

## Choose a format

Use these options in order:

1. Use Flatpak for desktop applications.
2. Use [Apx](apx) for development tools and distribution packages that can run
   in a subsystem.
3. Use the [VSO native subsystem](vso) for a Debian package that needs desktop
   integration but does not need to be part of the host image.
4. Add a package to a custom Vanilla OS image only when it must provide a
   driver, kernel module, early-boot service, or other host component.

Host package changes rebuild a future ABRoot state and take effect after a
reboot. Application packages do not normally need that cost or access.

## Custom image rules

Build custom images with [Vib](https://vib.vanillaos.org) and publish them as
OCI images compatible with the target Vanilla OS and CPU architecture.

Vanilla OS 3 keeps `/opt` and `/usr/local` as persistent paths backed by
`/var`. Do not place image-owned files at those paths. Package mutable data in
the correct persistent directory and keep user data under `/home`.

Test the image in a disposable installation before publishing it. Verify a
clean installation, an ABRoot upgrade, rollback, and host package application.

## Naming and versions

Keep the upstream project name unless the distribution package must avoid a
real naming conflict. Use the upstream version and add a packaging revision
when the package changes without a new upstream release, for example
`1.2.3-1`.

Never move a published package version backwards. Consumers and image builders
use version ordering to decide which package should be installed.
