+++
title = "Quick Start"
description = "A quick guide to using Trove and bpt."
date = 2022-07-05T08:00:00+00:00
updated = 2022-07-05T08:00:00+00:00
draft = false
weight = 10
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = 'A quick refresher guide to using Trove and bpt if you want to get started right away or just need a quick refresher.'
toc = true
top = false
+++

## Install bpt

Install bpt using one of the following commands (pulled from official [bpt docs](https://bpt.pizza/docs/latest/tut/install.html)). You will need `cURL` on Unix machines and `Invoke-WebRequest` on Powershell (Windows).

### Unix-like (Linux, MacOS)

```sh
# For Linux, writes file called `bpt` in curent working directory
curl bpt.pizza/get/linux -Lo bpt

# For MacOS, writes file called `bpt` in curent working directory
curl bpt.pizza/get/macos -Lo bpt

# For either, makes file an executable
chmod a+x bpt
```

### Powershell

```powershell
# Writes a file called `bpt.exe` in current working directory
Invoke-WebRequest bpt.pizza/get/windows -OutFile bpt.exe
```

## Install to PATH

While bpt is able to be a standalone tool in a project it can be added to the PATH using a sub-command.

```sh
./bpt install-yourself
```

## Start new Project

The easiest way to start a new bpt project is with the `bpt new` sub-command. It will ask you some options to help setup the project. For the most basic setup:

```sh
bpt new <project-name>
```

This will give you a `src/` directory, a `bpt.yaml` file and a `README.md` file. You use the `src/` directory to build you're application using headers and source files (like any C++ project). The `bpt.yaml` is used to specifiy dependencies, library use, your projects versions, test dependencies and other related infomation.

For more information of how packages are structured, checkout bpt's official docs. [bpt project structure →](https://bpt.pizza/docs/latest/design.html?highlight=directory%20structure)

bpt also has a "hello world" tutorial with a bit more information if you need. ["Hello World!" from bpt →](https://bpt.pizza/docs/latest/tut/hello-world.html)

## Adding a package from Trove

When you find a package you want to use from Trove simply specify the package's name in the dependency list within the `bpt.yaml` along with the relevent version constraints. The packages page should contain the relvent information regarding versions and libraries.

## Building with Trove

To build a bpt project that uses a package from Trove, you have to specify to bpt that you want to use Trove's package repository. This is down with the `--use-repo=""` flag with the `bpt build sub-command. This flag takes a string containing the URL to Trove's index.

```sh
bpt built -t <toolchain> --use-repo="https://trovepi.dev"
```

## Help

If you have trouble with any of the above instructions you can:

- Check out the help section for more information. [Help →](../../help/faq/)
- Reach out to me (oraqlle) at [oraqlle@github.com →](oraqlle@github.com)
- Open a 'Q&A' discussion on Trove's GitHub repository. [GitHub Q&A →](https://github.com/TrovePI/trove/discussions/categories/q-a)
- Check out the official bpt docs. They are more in depth and have more resources available and will remain up to date with the tool itself, (I do my best). [bpt docs  →](https://bpt.pizza/docs/latest/index.html)
