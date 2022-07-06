+++
title = "Starting a new bpt Project"
description = "Learn how to start a new project with bpt"
date = 2022-07-06T08:00:00+00:00
updated = 2022-07-06T08:00:00+00:00
draft = false
weight = 30
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "Starting a new project with a new build tool is sometimes scary and down-right annoying. bpt's got you covered with a super simple sub-command."
toc = true
top = false
+++

## New beginnings

bpt has a super simple sub-command for creating a new project for bpt. It is _drum roll..._

```sh
bpt new <project-name>
```

This will create a project called '_project-name_'. bpt will run you through a few steps on how you might want your project setup such as where you want the project to live and whether to split source and header files.

What you will find is three items in the newly created directory. A `README.md` file, a `bpt.yaml` file, a directory named `src/`.

- `README.md` - Contains a few lines with the name of the project and a short blanket description.
- `bpt.yaml` - This is the most important file. It contains information about the project's name, version, description, dependencies, test dependencies and library use.
- `src/` - This directory will contain a sub-directory named after the project with some basic code. This code just prints a messege.

<sub>Note<sup>1</sup>: If you decided to split headers and sources into `src/` and `include/` directories with `bpt new`, the template files will be split into their respective directories.</sub>

<sub>Note<sup>2</sup>: There is no main function/file in the new package, this is because bpt uses a special file extension to indicate _main_ and _test_ files. [Building an application with bpt →](https://bpt.pizza/docs/latest/guide/apps.html)</sub>

## Build a simple application with bpt

It's not covered here how to build a simple hello world with bpt here, that's available on the offical docs. ['Hello World!' from bpt →](https://bpt.pizza/docs/latest/tut/install.html#easy-mode-install-yourself)
