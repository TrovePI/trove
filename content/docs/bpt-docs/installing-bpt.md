+++
title = "Installing bpt"
description = "How to install bpt tool"
date = 2022-07-03T08:00:00+00:00
updated = 2022-07-31T08:00:00+00:00
draft = false
weight = 20
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = 'Here are a few ways to download and install bpt.'
toc = true
top = false
+++

## Downloading

### Pre-built Binaries

bpt has a few pre-built binaries that are available to download on a variety of platforms. [bpt's download page →](https://bpt.pizza/downloads/)

### From the Terminal

bpt is also available to be downloaded from the terminal using `cURL` (Linux, MacOS) or Powershells `Invoke-WebRequest`.

<sup>_Note: If on Linux or MacOS, `chmod` has to be used to make the file executable._</sup>

#### Unix-like (Linux, MacOS)

```sh
# For Linux, writes file called `bpt` in curent working directory
curl bpt.pizza/get/linux -Lo bpt

# For MacOS, writes file called `bpt` in curent working directory
curl bpt.pizza/get/macos -Lo bpt

# For either, makes file an executable
chmod a+x bpt
```

#### Powershell

```powershell
# Writes a file called `bpt.exe` in current working directory
Invoke-WebRequest bpt.pizza/get/windows -OutFile bpt.exe
```

## Installing

### Install Yourself!

bpt features a 'install yourself' sub-command that installs the binary into a predetermined path on your system and add the path to the `$PATH` environment variable. This is the easiest way to install bpt.

```sh
./bpt install-yourself
```

This command will move the executable to a predetermined local-user path on your system. On Windows this is the `%LocalAppData%/bin` directory and on Unix-like machines this is the `~/.local/bin` directory. It also ensures that this path is available to the current users `$PATH` variable.

### Other ways to install

If you need to manually change the `$PATH` of your machine on Windows or Unix-like machines, instructions can be found on the offical install page. [bpt's offical install page →](https://bpt.pizza/docs/latest/tut/install.html#easy-mode-install-yourself)
