# watch-and-do
Bash script that waits for changes on files of a directory(watch) and executes a command(do) when a change is detected.

# Getting Started
`watch-and-do` listen for changes in files of a directory. When a change is detected, then it waits a moment for more changes and if there are no more changes, then it executes a command. If the command is running when new changes are detected, then the process, where the command is running, is killed before starting a new process with a new execution of the command.

This bash script was created with the intention to watch changes in a folder of PHP code and then run unit tests with PHPUnit automatically. However it can be used to apply any command instead the PHPUnit command to run tests.

# Prerequisites

- [inotifywait](https://linux.die.net/man/1/inotifywait)

# Installation

1. Install the [prerequisites](#prerequisites) in your local system.
2. Clone this repository or download the file watch-and-do inside this repository to your local system.

# Usage

## Syntax
```
watch-and-do WATCHDIR COMMAND
```

- *WATCHDIR* is the path to the folder to listen for changes in files.
- *COMMAND* is the command to execute when a change is detected.

## Example
```
$ /path/to/watch-and-do ~/my-project phpunit --group users
```

In this example, `watch-and-do` is not installed globally, then the path to the script is used. The first argument, *~/my-project*, is the folder to watch for changes. The remaining is the command to execute. Note that *--group* and *users* are not arguments to *watch-and-do* but they are arguments to *phpunit*. The command could be a path to an executable script. In this example, phpunit is installed globally, so the path to the phpunit script is not required.

# License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
