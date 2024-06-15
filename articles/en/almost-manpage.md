---
Title: Almost Manpage
Description: Manpage for the almost utility.
PublicationDate: 2023-06-10
Authors: 
  - Vanilla-OS
Tags:
  - almost
  - manpage
---

> Note: `almost` has been replaced with `abroot`.

## NAME

```md
almost - an on-demand immutability and layering tool based on the (i)mmutable file attribute and tmpfs.
```

## SYNOPSIS

```md
almost [OPTIONS] [COMMAND] [ARGS]
```

## DESCRIPTION

```md
almost is a utility that provides on-demand immutability by toggling the immutability of files and directories in the system root. It also provides a way to create layers on top of immutable directories, allowing you to test changes before committing them.

Options:
	--help/-h		show this message
	--verbose/-v		verbose output
	--version/-V		show version

Commands:
	enter			set the filesystem as ro or rw until reboot
	config			show the current configuration
	check			check whether the filesystem is read-only or read-write
	run			runs a command in read-write mode and returns to read-only mode after the command exits
```

## ENTER

```md
Set the filesystem as read-only or read-write until reboot.

Setting the filesystem to read-write mode could be a security risk, be
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

```md
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

```md
Check whether the filesystem is read-only or read-write.

Usage:
check [options] [command]
Options:
	--help/-h		show this message
Examples:
	almost check
```

## RUN

```md
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

- [`apx`](apx)

## DIAGNOSTICS

```md
almost returns 0 on success, 1 on error.
```

## AUTHOR

```md
Contributors of Vanilla OS
```

## REPORTING BUGS

Report bugs to the [issue tracker](https://github.com/Vanilla-OS/almost/issues).
