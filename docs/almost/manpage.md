---
title: Manlpage almost - Vanilla OS
description: Manpage for the almost utility.
---

# Manpage `almost`

## NAME
```
almost - an on-demand immutability and layering tool based on the (i)mmutable file attribute and tmpfs.
```

## SYNOPSIS
```
almost [OPTIONS] [COMMAND] [ARGS]
```

## DESCRIPTION
```
almost is a utility that provides immutability on demand by toggling the immutability of files and directories in the system root. It also provides a way to create layers on top of immutable directories, allowing you to test changes before committing or dropping them.

Options:
	--help/-h		show this message
	--verbose/-v		show more verbosity
	--version/-V		show version

Commands:
	enter			set the filesystem as ro or rw until reboot
	config			show the current configuration
	check			check whether the filesystem is read-only or read-write
	run			runs a command in read-write mode and returns to read-only mode after the command exits
```

## ENTER
```
Set the filesystem as read-only or read-write until reboot.

Setting the filesystem as read-write mode may consist of a security risk, be
careful when using this command.

Usage:
    enter [options] [command]

Options:
	--help/-h		show this message
	--verbose/-v		verbose output

Commands:
	ro			set the filesystem as read-only
	rw			set the filesystem as read-write
	default			set the filesystem as defined in the configuration file

Examples:
	almost enter ro
	almost enter rw
```

## CONFIG
```
Manage and show the current configuration.

Usage:
    config [options] [command]

Options:
    --help/-h		show this message

Commands:
    set [key] [value]	set a configuration value

Examples:
    almost config
    almost config set Almost::DefaultMode 1
```

## CHECK
```
Check whether the filesystem is read-only or read-write.

Usage:
check [options] [command]
Options:
	--help/-h		show this message
Examples:
	almost check
```

## RUN
```
Runs a command in read-write mode and returns to read-only mode after the command exits.

Usage:
    run [command]
Options:
	--help/-h		show this message
	--verbose/-v		verbose output
Examples:
    almost run ls
```

## SEE ALSO
- [`apx`](/docs/apx)

## DIAGNOSTICS
```
almost returns 0 on success, 1 on error.
```

## AUTHOR
```
Contributors of Vanilla OS
```

## REPORTING BUGS
Report bugs to the [issue tracker](https://github.com/Vanilla-OS/almost/issues).