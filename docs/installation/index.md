---
title: Vanilla OS Installation
description: Learn how to install Vanilla OS to your device.
---

# Preparation

## You will need
- A flash drive with at least 8GB of capacity.
- A drive with at least 25GB of storage space.
- 30 minutes to an hour of your time.

## Creating a bootable USB stick
This section will guide you through creating a bootable USB stick with Vanilla OS on it.

### Downloading Vanilla OS
First, download the Vanilla OS disk image that will be written to your USB flash drive from [here](https://vanillaos.org/).

### Installing Etcher
To flash the disk image to your USB stick, download and install [balenaEtcher](https://www.balena.io/etcher/).

If you wish, you can also use different software that you are familiar with, such as [Ventoy](https://www.ventoy.net/) or [Rufus](https://rufus.ie/).

### Flashing the image
**Warning**: this will erase **all data** on your USB flash drive. Make sure to back up all your important data before proceeding!

Open Etcher, select the downloaded disk image and your USB flash drive, then click "Flash!".

![Flashing](/assets/uploads/installation-flashing.webp)

When the process is done, you will have a bootable USB stick with Vanilla OS on it.

## Booting from the USB flash drive
Insert the USB flash drive in the computer that you want to install Vanilla OS to and power up or restart the device.

If your device does not automatically boot into the Vanilla OS installation media, restart and while the device is starting up, hold down the key to `select boot device` or for `boot menu` indicated by a prompt on the boot screen. The most common keys are F2, F10, F11, F12, Delete and Escape. If the prompt isn't present, try searching online for your specific model. Select Vanilla OS or the model of your USB flash drive from the boot menu.

When your device has succesfully booted from the USB stick, you should see a Welcome screen inviting you to either try or install Vanilla OS.

![Welcome](/assets/uploads/installer-welcome.webp)

You can try Vanilla OS without making any changes to your device. If you are satisfied, you can re-open the installer (the first icon in the dash) and proceed with the installation.

# Installing Vanilla OS

## First steps
Click "Install Vanilla OS" and set your preferred language, keyboard layout and timezone.

## Types of installation
Depending on whether you want to dual- or multiboot Vanilla OS alongside other operating systems, you will need to follow different steps when selecting your disk.

This guide will help you with the following types of installation:
- [Installing only Vanilla OS](/docs/installation/#title8)
- [Installing alongside Windows](/docs/installation/#title9)
- [Advanced installation](/docs/installation/#title14)

## Installing only Vanilla OS
This section will guide you through installing Vanilla OS to an entire disk, **erasing all previous data on it**. Make sure to back up all your important data before proceeding!

Select the disk you want to install Vanilla OS to, click "Configure", select "Use Entire Disk", click "Apply" and review your changes.

![Use Entire Disk](/assets/uploads/installer-use-entire-disk.webp)

Create your user account and review the changes that will be made to your system. Click on "Install Vanilla OS" and the installation will begin.

![Confirming the installation](/assets/uploads/installer-confirm-installation.webp)

## Installing alongside Windows
This section will guide you through installing Vanilla OS on the same drive as an existing Windows installation.

If you wish to install Vanilla OS on the same computer, but on a different drive than Windows, follow the steps described in [Installing only Vanilla OS](/docs/installation/#title8).

### Opening GParted
Select the disk that Windows is installed on and click "Configure". Select "Manual Partitioning" and click on the arrow next to it. Click on "Open GParted" to manually partition your disk.

![Manual Partitioning](/assets/uploads/installer-manual-partitioning.webp)

### Resizing your C: drive
Once you are in GParted, you will see a visual representation of your disks' partitions. In the top right corner, select the disk that Windows is installed on. Select the `ntfs` partition equivalent to your Windows `C:` drive (usually the biggest one). If you are unsure which one that is, reboot to Windows, open Disk Management and check the partitions against the ones displayed here.

Right click on the selected partition and click "Resize/Move". Here, you can drag either edge of the partition to make it smaller. You can also configure the exact new size of the partition at the bottom.

![Shrinking your C: drive](/assets/uploads/installation-shrink-c.webp)

Once you shrank it by how much space you want to take from Windows and dedicate to Vanilla OS (at least 25GB), click "Resize/Move".

### Creating the new partitions
After shrinking your Windows partition, you will be left with unallocated space. You will have to create 2 partitions in this space. Right click on it and select "New".

Create a 1024MB partition with an `ext4` file system. Click "Add". This will be your `/boot` partition.

![Creating your /boot partition](/assets/uploads/installation-create-boot.webp)

Select "New" on the unallocated space again. Use the entirety of the remaining space to create a partition with a `btrfs` file system. Click "Add". This will be your `/` partition.

![Creating your / partition](/assets/uploads/installation-create-root.webp)

Click "Apply All Operations" \(the checkmark in the toolbar\) and when it's finished, close GParted.

### Selecting the new partitions
Click on your newly created partitions, then select their formats and mount points as `btrfs` and `/` for the bigger one and `ext4` and `/boot` for the 1024MB one. You might need to close and re-open the installer for the new partitions to appear.

![Selecting partitions](/assets/uploads/installer-select-boot.webp)

Open GParted and see if you have a partition that reads "EFI System Partition" (if you have a modern computer, you most likely will). If so, select `/boot/efi` as its mount point and leave the format on "Do not touch".

Click "Apply" and review your changes.

Create your user account and review the changes that will be made to your system. Click on "Install Vanilla OS" and the installation will begin.

![Confirming the installation](/assets/uploads/installer-confirm-installation.webp)

## Advanced installation
This section will help you with manual partitioning in case your particular needs for installation aren't covered by this guide.

Select the disk that you want to install Vanilla OS to and click "Configure". Select "Manual Partitioning" and click on the arrow next to it. Click on "Open GParted" to manually partition your disk.

![Manual Partitioning](/assets/uploads/installer-manual-partitioning.webp)

After you're done, select mount points and file systems for each of your partitions. You might need to close and re-open the installer for new partitions to appear.

Click "Apply" and review your changes.

Create your user account and review the changes that will be made to your system. Click on "Install Vanilla OS" and the installation will begin.

![Confirming the installation](/assets/uploads/installer-confirm-installation.webp)

# Booting into Vanilla OS
## If you only have Vanilla OS installed
After the installer finishes, all you need to do is reboot and remove the USB stick. Vanilla OS will be waiting for you.

## If you dual- or multiboot
### On the same drive
After the installer finishes, all you need to do is reboot and you will see a boot menu with your installed operating systems. Select Vanilla OS, wait for it to boot and remove the USB stick.

### On different drives
After the installer finishes, you need to reboot and select Vanilla OS from your device's boot menu that you can access by holding down a specific key while the device is starting up indicated by a prompt on the boot screen. If the prompt isn't present, try searching online for your specific model. Once you're in Vanilla OS, remove the USB stick.

You can configure the default boot order in your device's firmware settings.