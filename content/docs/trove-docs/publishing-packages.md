+++
title = "Publishing Packages"
description = "Learn how to publish packages to Trove."
date = 2022-07-10T08:00:00+00:00
updated = 2022-07-11T08:00:00+00:00
draft = false
weight = 30
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "So, you want to publish your packages to Trove. That's great! While Trove doesn't have and isn't a CLI tool to publish packages automatically you can add them manually through forking and created a pull request on this repository directory."
toc = true
top = false
+++

## Package Structure

Fist and foremost, for a package to be published to Trove is has to be a valid bpt package in itself. This means it has to have a valid `bpt.yaml` file and be 'packagable' with bpt's package creation command `bpt pkg create`.

For them to be accepted to Trove, they have to have the following files:

- README.md
  - Details on what the package does.
  - Any toolchains needed.
  - C++ standard needed/available.
  - Compiler support.
  - Any other special build and configuration setup.
  - Indicate if any external/custom package repos are used.
- LICENSE/LICENSE.md
- CODE_OF_CONDUCT.md

A GitHub template is available on the TrovePI GitHub page. [Template →](https://github.com/TrovePI/trove-template)

<sup>Note<sup>1</sup>: The files can have different names, the important part is the infomation they contain.</sup>

## Setting Up Package

To prepare your package for Trove you have to 'package up' you project. In your project root directory, run the command:

```sh
bpt pkg create
```

This will create a tarball file to export (a `*.tar.gz` file).

<sup>Note<sup>2</sup>: If you need to repackage your project, you can specifiy the revision of the current package version with `bpt pkg create --revision=<num>`</sup>

## Adding to Trove

Before you can go any further, you will need a valid installion of bpt and git on your system. You will also need a GitHub account.

### Cloning Trove

Cloning Trove is simple if you are familar with git. Use the following command to clone Trove into the current directory.

```sh
git clone https://github.com/trovepi/trove.git
```

### Adding to Package Database

Go to your projects root (or wherever your packages tarball is) and run the following command:

```sh
bpt repo import <path/to/trove/static> --if-exists=replace .
```

<sup>Note<sup>3</sup>: Don't forget the dot at the end.</sup>

This will add the package to the bpt database stored in Trove's static folder.

### Adding Package Documentation

h

## Making a Pull Request

### Pull Request Details

g

## Await Review
