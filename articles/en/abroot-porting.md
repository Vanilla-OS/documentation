---
Title: Porting ABRoot v1 to your distribution
Description: Find out how to port ABRoot v1 to your distribution.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

> This documentation refers to ABRoot v1, not v2. The documentation for v2 is still being written.

# Porting ABRoot to your distribution

ABRoot is a technology that can be used to bring atomic transactions to any Linux distribution. However, it may require some additional setup or configuration in order to function properly with different setups. 

The instructions provided in this documentation are general guidelines, and may require some adjustments to work on your specific Linux distribution. To properly use and configure ABRoot, a basic understanding of how Linux works, including knowledge of the package manager, the common file structure of a Linux root partition and what atomicity is, is necessary. It is important to consult the documentation for specific details and make any necessary adaptations.

Also a good understanding of what ABRoot is and how it works is necessary to properly port it to your distribution. If you are not familiar with ABRoot, please read the [ABRoot documentation](/docs/ABRoot/index) first.

### Possible changes needed to the system

There are some possible changes you might need to apply to your system to make it compatible with ABRoot. This list only works as a starting point and not a to-do list. Your system may already be compatible with ABRoot without any modifications or with many others that are not foreseen in this documentation, so it is important to be prepared to troubleshoot and experiment. 

Some possible changes include:

- Updating the kernel to a newer version
- [Patch the `grub-mkconfig` script](https://bugs.launchpad.net/ubuntu/+source/grub2/+bug/1247905) to support the `overlay` file system, needed during the transaction
- Make some custom hooks to prevent some binaries to be executed outside of the transactional shell, like the package manager command line or prevent the package manager to update some files you may want to patch
- Patch one or more software to support the [ABRoot file system structure](#file-system-structure)
- Patch other software to prevent them from installing files in the root partition since it should be updated only during the transaction
- Write your own way to make the [protected directories](#protected-directories) immutable, like using a systemd unit
- Make some custom mount points to mount some directories as a bind mount, like `/var`, to make software like Flatpak work properly since it reads the symlink of `/var` to its protected directory, breaking some applications

### File system structure

ABRoot uses a custom file system structure to allow for atomic transactions. It is designed to be compatible with the classic file system structure, but there are some differences.

The following is the structure of a root partition with ABRoot:

```
.
├── bin -> .system/usr/bin
├── boot
├── dev
├── etc -> .system/etc
├── home
├── lib -> .system/usr/lib
├── lib32 -> .system/usr/lib32
├── lib64 -> .system/usr/lib64
├── libx32 -> .system/usr/libx32
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin -> .system/usr/sbin
├── srv
├── sys
├── tmp
├── usr -> .system/usr
└── var
```

As you can see, some directories are now symlinks to the `.system` directory, which is the true root of the system. This is done to allow ABRoot to switch the content of the root partition in a atomic way.

It's important to note that, the libs directories can be different in other distributions and you may need to patch ABRoot to support a different layout. 

### Protected directories

Protected Directories in ABRoot are a crucial aspect of its design, as they ensure that the essential components of the system are protected from accidental or unintended modifications. These directories are considered vital to the proper functioning of the system and any changes made to them can have severe consequences on the system's stability and security.

`/usr` is the recommended directory to protect, as it contains the packages and libraries necessary for the system to operate. Protecting this path is crucial in preventing system crashes, security breaches, or general instability. It also ensures the integrity of the packages and libraries, and prevents any unintended changes from occurring. To make any changes to this path, it is necessary to use the ABRoot's transaction mechanism. This guarantees that any changes made will be atomic and will not affect the system stability and security.

### Getting started

It is recommended to work with the ABRoot code directly, rather than using any packaged version. This allows for better debugging and making changes to the code, as well as ensuring that you are using the most up-to-date version of the software. In order to do this, you will need to install **Go** (version **1.19.2 or later**), and clone the ABRoot repository from the [Vanilla OS Github Organization](https://github.com/Vanilla-OS/ABRoot). 

Then build the `abroot` binary with the following command:

```bash
go build -o abroot
```

#### Setting up the environment

For better testing and security purposes, it is recommended to use a virtual machine (VM) since ABRoot need a specific partitioning to works. 

The following is the recommended partitioning for the VM:

- 1 partition for the boot
- 2 root partitions (labeled "a" and "b") of the same size (at least 20GB, but this can vary depending on the distribution)
- 1 for the home

To make sure that the testing environment is not affected by the changes you made it is recommended to take a snapshot of the setup when it is ready, so you can revert it without re-initializing the VM every time a test goes wrong.

#### Initial testing

Once the VM is set up, you should copy the abroot binary you built to the `/usr/bin` directory. Then, you can start testing by running the command `abroot get present` to ensure that the setup is correct. It will raise an error if the A/B structure is not correct, so you may need to re-partition the VM to fix it.

> The recommended way to run any test is entering a root session and export the `ABROOT_VERBOSE=1` environment variable for gain more verbosity. 

Next, you can try starting a transactional shell. If the command failed it means that there are some incompatibilities with the system that we should fix. 

This task can vary from distribution to distribution and the `ABROOT_VERBOSE` variable helps in this as it lists all operations that are performed, including errors. This will allow you to identify what changes you need to make.

To fix a compatibility problem like apply a patch on the fly, consider using the hook system of ABRoot, just by placing your custom shell scripts in `/etc/abroot/start-transaction-rules.d` and `/etc/abroot/end-transaction-rules.d`. The start scripts run right before the shell opens and end scripts run when the shell is closed. Note that when the shell is closed, ABRoot starts the atomic transaction, so you cannot run any commands that will modify the system.

#### Final considerations

I know that this documentation does not cover all the possible problems that can occur when porting ABRoot to a new distribution, but this is intended to be a starting point. Predicting all the possible problems that can occur is impossible, so it is important to be prepared to troubleshoot and experiment.

If you have any questions or suggestions, feel free to open an issue in the [ABRoot repository](https://github.com/vanilla-os/ABRoot/issues).
