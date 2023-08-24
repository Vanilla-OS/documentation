---
Title: Packaging 
Description: Find out how to package software and libraries for Vanilla OS.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

# Packaging

Packaging is the process of creating a package for a software or library, so that
it can be installed on a distribution. Vanilla OS has a unconventional root
filesystem layout, which requires some considerations and guidelines to be
followed.

## When to Package?

Vanilla OS is a transactional distribution, which means that it receives
updates through transactions. The process is handled by [ABRoot](/docs/ABRoot),
which requires a reboot to apply the changes. This means that the user will
have to reboot the system after installing a package, and this is not ideal.
Also the root partition is very small, this is intentional to prevent the user
from installing too many packages, which would expose the system to security
vulnerabilities and complexity during the transactions.

For these reasons, it is recommended to package only essential software and
libraries. To better understand what is essential, you can check the following
table:

| Software | Essential | Reason                                                                                                                                                                                                                                                    |
| -------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Chromium | No        | It is a web browser, which is not essential for the system and can be installed via [Apx](/docs/apx), [Flatpak](https://handbook.vanillaos.org/2022/12/09/install-flatpaks.html), [Snap](https://snapcraft.io/) or [AppImage](https://appimage.org/).     |
| fuse     | Yes       | This is a device driver, which is essential for AppImage to work, and must be also installed from outside the Apx container.                                                                                                                              |
| GIMP     | No        | It is a graphics editor, which is not essential for the system and can be installed via [Apx](/docs/apx), [Flatpak](https://handbook.vanillaos.org/2022/12/09/install-flatpaks.html), [Snap](https://snapcraft.io/) or [AppImage](https://appimage.org/). |

## Packaging Guidelines

This section is organized in multiple subsections, each one describing a
different aspect of the packaging process.

### Naming

There are no restrictions on the name of the package, but it is recommended to
use the same name as the upstream project. I.e. if the upstream project is
called `foo`, the package should be called `foo`, and not `bar`. This is
important because it allows the user to easily identify the package.

### Versioning

The version of the package should be the same as the upstream version, with
minor changes if needed. For example, if the upstream version is `1.2.3`, the
package version should be `1.2.3`, and not `2.0.0`. If the package has some
minor changes, the version should be `1.2.3-1`, `1.2.3-2`, etc. The version
must never go backwards or forwards the upstream version.

### Storage

Some applications require a lot of storage, and this can be a problem for
Vanilla OS, which has a small root partition. If the application cannot be
installed in the Apx container or any other way, it is recommended to edit
its behavior to locate its data in the user's home directory or in the `/home`
partition, which has a lot more storage.

This is also a good practice, since it allows the user to easily backup the
data of the application, and also to easily remove the application without
losing the data.
