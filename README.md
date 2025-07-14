# dirwalk.sh

## Overview

`dirwalk.sh` is a lightweight, POSIX-compliant shell script for recursively traversing directories in Unix-like systems. It offers customizable traversal modes (`parents` or `children`) and supports exclusion of specific paths during the scan. This utility is ideal for sysadmins, DevOps engineers, and power users looking to automate filesystem analysis or manage large directory trees with precision.

## Features

- 🔁 Recursive directory traversal with ordering control.
- 🚫 Exclude specific directories from the traversal using a pipe-separated list.
- ⚡ Fast, efficient, and dependency-free (pure shell).
- 🧩 Compatible with Unix-like operating systems.

## Usage

```sh
dirwalk.sh [OPTIONS] MODE MOUNT_POINT [EXCLUDE_PATHS]
```

### Arguments

- `MODE`: Traversal mode, either:
  - `parents` – prints directories before traversing subdirectories
  - `children` – prints directories after traversing subdirectories
- `MOUNT_POINT`: Base directory to start traversal from.
- `EXCLUDE_PATHS`: *(Optional)* Pipe-separated list of absolute paths to exclude.

### Examples

Traverse and print parent directories:

```sh
./dirwalk.sh parents /
/
```

Traverse and print children directories:

```sh
./dirwalk.sh children /
/bin
/boot
/dev
/etc
/home
/lib
/lib64
/lost+found
/media
/mnt
/opt
/path
/proc
/root
/run
/sbin
/srv
/sys
/tmp
/usr
/var
```

Traverse directory with exclusions:

```sh
./dirwalk.sh parents / "/usr/local|/proc"
/
/usr
```

Traverse child directories with exclusions:

```sh
./dirwalk.sh children / "/usr/local|/proc"
/bin
/boot
/dev
/etc
/home
/lib
/lib64
/lost+found
/media
/mnt
/opt
/path
/root
/run
/sbin
/srv
/sys
/tmp
/usr/bin
/usr/games
/usr/include
/usr/lib
/usr/lib64
/usr/libexec
/usr/sbin
/usr/share
/usr/src
/var
```

## Requirements

- POSIX-compliant shell (`/bin/sh`)

## Contributing

Contributions are welcome! If you have ideas for improvement or fixes, feel free to fork the repository and submit a pull request. Be sure to follow conventional shell scripting best practices.

## License

This project is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
