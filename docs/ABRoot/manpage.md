---
title: Manpage ABRoot - Vanilla OS
description: Manpage for the ABRoot utility.
---

# Manpage `abroot`

## NAME

```text
ABRoot is a utility that provides complete immutability and atomicity by transacting between 2 root partitions (A⟺B), it also allows for on-demand transactions via a transactional shell.
```

## SYNOPSIS

```text
abroot [options] [command]
```

## DESCRIPTION

```markdown
Usage:
    abroot [options] [command]

Options:
    --help/-h       show this message
    --verbose/-v        show more verbosity
    --version/-V        show version

Commands:
    _update-boot    update the boot partition (for advanced users only)
    get             outputs the present or future root partition state
    shell           enter a transactional shell in the future root partition and switch root on the next boot
    exec            execute a command in a transactional shell in the future root partition and switch to it on the next boot
```

## EXEC

```markdown
Execute a command in a transactional shell in the future root partition and switch to it on the next boot.

Usage:
    exec [command]

Options:
    --help/-h           show this message
    --assume-yes/-y     assume yes to all questions

Examples:
    abroot exec ls -l /
    abroot exec apt install git 
```

```text
Tip: You can enclose multiple commands using "" and pass it as a single string.
```

### GET

```markdown
Outputs the present or future root partition state (A or B).

Usage:
    get [state]

Options:
    --help/-h       show this message

States:
    present     get the present root partition state
    future      get the future root partition state

Examples:
    abroot get present
    abroot get future
```

## SHELL

```markdown
Enter a transactional shell in the future root partition and switch root on the next boot.

Usage:
    shell

Options:
    --help/-h           show this message
    --assume-yes/-y     assume yes to all questions

Examples:
    abroot shell
```

## UPDATE BOOT

```markdown
Update the boot partition for maintenance purposes (for advanced users only).

Usage:
    _update-boot

Options:
    --help/-h           show this message
    --assume-yes/-y     assume yes to all questions
```

## SEE ALSO

- [`apx`](/docs/apx)
- [`vso`](/docs/vso)

## AUTHOR

```text
Contributors of Vanilla OS
```

## REPORTING BUGS

Report bugs to the [issue tracker](https://github.com/Vanilla-OS/ABRoot/issues).
