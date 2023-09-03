---
Title: VSO Manpage
Description: Manpage for the Vanilla System Operator utility.
PublicationDate: 2023-09-03
Authors: Contributors of Vanilla OS
---

## NAME

```md
The Vanilla System Operator (VSO) is a package manager, a system updater and a task automator
```

## SYNOPSIS

```md
vso [command] [arguments] [options]
```

## DESCRIPTION

```md
The Vanilla System Operator is a package manager, a system updater and a task automator.

Usage:
  vso [command]

Available Commands:
  completion  Generate the autocompletion script for the specified shell
  config      Manage the system configuration.
  export      Export an application or binary from the subsystem
  help        Help about any command
  install     Install an application inside the subsystem
  pico-init   Initialize the Pico subsystem, used for package management
  remove      Remove an application from the subsystem
  run         Run an application from the subsystem
  search      Search for an application to install inside the subsystem
  shell       Enter the subsystem environment
  sys-upgrade Upgrade the system
  tasks       Create and manage tasks
  unexport    Unexport an application or binary from the subsystem
  update      Update the subsystem's package repository
  upgrade     Upgrade the packages inside the subsystem

Flags:
  -h, --help      help for vso
  -v, --version   version for vso

Use "vso [command] --help" for more information about a command.
```

## COMPLETION

```md
Generate the autocompletion script for vso for the specified shell.
See each sub-command's help for details on how to use the generated script.

Usage:
  vso completion [command]

Available Commands:
  bash        Generate the autocompletion script for bash
  fish        Generate the autocompletion script for fish
  powershell  Generate the autocompletion script for powershell
  zsh         Generate the autocompletion script for zsh

Flags:
  -h, --help   help for completion

Use "vso completion [command] --help" for more information about a command.
```

## CONFIG

```md
Manage the system configuration.

Usage:
  vso config [command]

Available Commands:
  get         Get the system configuration
  set         Set the system configuration
  show        Show the system configuration

Flags:
  -h, --help   help for config

Use "vso config [command] --help" for more information about a command.
```

## EXPORT

```md
Export an application or binary from the subsystem

Usage:
  vso export [flags]

Flags:
  -a, --app string   the name of the application to export
  -b, --bin string   the name of the binary to export
  -h, --help         help for export
```

## INSTALL

```md
Install an application inside the subsystem

Usage:
  vso install [flags]

Flags:
  -h, --help   help for install
```

## PICO-INIT

```md
Initialize the Pico subsystem, used for package management

Usage:
  vso pico-init [flags]

Flags:
  -f, --force   force the initialization if the subsystem is already initialized
  -h, --help    help for pico-init
```

## REMOVE

```md
Remove an application from the subsystem

Usage:
  vso remove [flags]

Flags:
  -h, --help   help for remove
```

## RUN

```md
Run an application from the subsystem

Usage:
  vso run [flags]

Flags:
  -h, --help   help for run
```

## SEARCH

```md
Search for an application to install inside the subsystem

Usage:
  vso search [flags]

Flags:
  -h, --help   help for search
```

## SHELL

```md
Enter the subsystem environment

Usage:
  vso shell [flags]

Flags:
  -h, --help   help for shell
```

## SYS-UPGRADE

```md
Upgrade the system

Usage:
  vso sys-upgrade [command]

Available Commands:
  check       Check for system updates
  upgrade     Upgrade the system

Flags:
  -h, --help   help for sys-upgrade

Use "vso sys-upgrade [command] --help" for more information about a command.
```

### SYS-UPGRADE CHECK

```md
Check for system updates

Usage:
  vso sys-upgrade check [flags]

Flags:
  -x, --as-exit-code   checks for upgrade but doesn't print anything. Return exit code 0 if no upgrade is available and 1 otherwise.
  -h, --help           help for check
  -j, --json           output the result in JSON format
```

### SYS-UPGRADE UPGRADE

```md
Upgrade the system

Usage:
  vso sys-upgrade upgrade [flags]

Flags:
  -h, --help   help for upgrade
  -n, --now    Trigger a system upgrade now
```

## TASKS

```md
Create and manage tasks

Usage:
  vso tasks [command]

Available Commands:
  list        List all tasks
  new         Create a new task
  rm          Remove a task
  rotate      Rotate tasks

Flags:
  -h, --help   help for tasks

Use "vso tasks [command] --help" for more information about a command.
```

### TASKS LIST

```md
List all tasks

Usage:
  vso tasks list [flags]

Flags:
  -h, --help   help for list
  -j, --json   output the tasks in JSON format
```

### TASKS NEW

```md
Create a new task

Usage:
  vso tasks new [flags]

Flags:
  -y, --assume-yes                    assume yes for all prompts
      --at string                     schedule the task to execute at a specific time (hh:mm)
      --command string                specify the command to execute
      --description string            specify the task's description
      --every string                  schedule the task to execute every X time (minutes, hours, days)
  -h, --help                          help for new
      --name string                   specify the task's name
      --need-confirm                  ask for confirmation before executing the task
      --on-battery                    execute the task only when the system is on battery
      --on-charge                     execute the task only when the system is charging
      --on-condition-command string   execute the task on condition command
      --on-cpu-temp string            execute the task when CPU temperature is higher than 60\C2\B0C
      --on-cpu-usage string           execute the task when CPU usage is higher than X%
      --on-device-connect string      execute the task when a device is connected
      --on-device-disconnect string   execute the task when a device is disconnected
      --on-disconnect                 execute the task when the system is disconnected from the network
      --on-full-battery               execute the task when the system is fully charged
      --on-high-cpu-usage             execute the task when CPU usage is higher than 50%
      --on-high-internet-usage        execute the task when internet usage is higher than 500Kb/s
      --on-high-memory-usage          execute the task when memory usage is higher than 50%
      --on-internet-usage string      execute the task when internet usage is higher than XKb/s
      --on-low-battery                execute the task when the system is low on battery (20%)
      --on-memory-usage string        execute the task when memory usage is higher than X%
      --on-network                    execute the task when the system is connected to the network
      --on-process string             execute the task when a process starts
```

### TASKS RM

```md
Remove a task

Usage:
  vso tasks rm [flags]

Flags:
  -f, --force         force the deletion of the task
  -h, --help          help for rm
  -n, --name string   specify the task's name
```

### TASKS ROTATE

```md
Rotate tasks

Usage:
  vso tasks rotate [flags]

Flags:
  -h, --help                   help for rotate
  -e, --private-event string   specify private event to rotate tasks for boot, shutdown, login, logout
```

## UNEXPORT

```md
Unexport an application or binary from the subsystem

Usage:
  vso unexport [flags]

Flags:
  -a, --app string   the name of the application to unexport
  -b, --bin string   the name of the binary to unexport
  -h, --help         help for unexport
```

## UPDATE

```md
Update the subsystem's package repository

Usage:
  vso update [flags]

Flags:
  -h, --help   help for update
```

## UPGRADE

```md
Upgrade the packages inside the subsystem

Usage:
  vso upgrade [flags]

Flags:
  -h, --help   help for upgrade
```

## SEE ALSO

- [`apx`](apx)
- [`abroot`](vso)

## REPORTING BUGS

Report bugs to the [issue tracker](https://github.com/Vanilla-OS/vanilla-system-operator/issues).
