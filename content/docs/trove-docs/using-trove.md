+++
title = "Using Trove with bpt"
description = "How to use Trove"
date = 2022-07-03T08:00:00+00:00
updated = 2022-07-11T08:00:00+00:00
draft = false
weight = 20
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "Using Trove with the bpt CLI is super easy."
toc = true
top = false
+++

## Using Trove

Many of bpt's commands feature a `--use-repo=""` or `-r ""` flags. This allows bpt to consult and utilise external CRS repositories (ie. other package repositories made for bpt). This allows you to build, search and prefetch packages from external repositories.

### Build

A potential build command for a bpt project might look like:

```sh
bpt build -t :c++17:gcc
```

If your project uses a package from Trove and you try to build it with a command similar to the one above, bpt will fail the building saying the dependencies could not be resolved. This is because bpt has no notion of external dependencies unless it is told to use them. To use Trove, the commands must use the `--use-repo=""` or `-r ""` flags. The argument taken by the flag is a string containing a URL (or directory) to the package repository. In our case, using Trove's URL works.

```sh
bpt build -t :c++17:gcc -r "https://trovepi.dev"
```

### Search

bpt allows you to fuzzy search for packages. To search Trove from the command line you can use the `--use-repo=""` or `-r ""` flags.

```sh
bpt pkg search -r "https://trovepi.dev" "c*"
```

<sup>Note: the "c*" is the search query. Finds any package starting with the letter 'c'.</sup>

### Prefetch

You can also prefetch Trove's meta-data and check your copy is still 'fresh'.

```sh
bpt pkg prefetch -r "https://trovepi.dev/"
```

## Excluding the Default Repository

You may have noticed that when running these commands, it also searched the default repository. If you wish to not search the default repository you can use the `--no-default-repo` or `-NDR` flags.

```sh
bpt build -t c++17:gcc -NDR -r "https://trovepi.dev"
```

## Related docs

- bpt's official docs on remote package repos. [Remote Packages and Repositories →](https://bpt.pizza/docs/latest/guide/remote-pkgs.html)
