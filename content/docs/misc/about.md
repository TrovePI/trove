+++
title = "About"
description = "About Trove"
date = 2022-07-03T08:00:00+00:00
updated = 2022-07-09T08:00:00+00:00
draft = false
weight = 10
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = 'Trove is a Package Index for C++ packages and projects that use the bpt build tool.'
toc = true
top = false
+++

## Why Does Trove Exist?

At the time of building/writing, bpt is only in it's first beta. As such much of it's development is focused on improving the tool core functionality and usability, leaving the default package repository much to be desired.

As such Trove aims to fill this gap and provide a much more dynamic interface to view and share packages and learn how to get started with bpt.

Trove also aims to facilitate the development of new and existing C++ projects to built using bpt by providing a place for projects to be published and fostering a community to help improve the tools used in development of C++ code.

## What about bpt's Default Repository?

While bpt comes with a default package repo with some very popular libraries/packages available, these packages are ports and thus aren't maintained by the library's contributors and maintainers. There also doesn't exist a bpt-standard way to publish new packages bpt's default repository.

Trove, while not a tool, will have a development pipeline (through GitHub issues and pull requests) for updating it's catalogue, allowing people to test develop packages and also have them available to users.

## Why doesn't bpt use Trove by default?

Well for one, at the time of writing Trove has a very small catalogue and is in itself still in development. Trove is also developed completely independent of bpt.
