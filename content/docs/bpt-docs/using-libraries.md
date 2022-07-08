+++
title = "Building and using Libraries"
description = "Learn how to build and use libraries."
date = 2022-07-06T08:00:00+00:00
updated = 2022-07-07T08:00:00+00:00
draft = false
weight = 50
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "Sometimes you will want or need to breaking your project into libraries. In that case, bpt makes it super easy to specify your library's dependencies (normal and test)."
toc = true
top = false
+++

Libraries are sub-components of a package. In bpt, you can specify which libraries are in use by your project or your libraries. We've already seen an example of this for the test dependency `catch2`. On the previous page we saw that we used the `main` library from catch2.

```yaml
test-dependencies:
  - catch2@2.13.9 using main
```

This indicates to bpt that we want to use catch2's `main` library across our entire package (well, across all the `.test.cpp` files). However, you can also specify that you want only a particular library in your project to access an external dependencies library.

## Making and Using Libraries

Before we continue, I'll show what a simple multi-library project's `bpt.yaml` might look like.

In the below sample `bpt.yaml` describes have a project named 'hello'. It has a global dependency on `printer` and has the test dependecy on `tester`. The project has two libraries, `foo` and `bar`. `foo` depends on the external packages `logger` and `app-maker` and uses library called `gui` from one of it's dependencies (assumed to be `app-maker`). `bar` uses the internal library `foo`.

```yaml
name: hello
version: 0.1.0

dependencies:
  - printer@0.1.0  # Globally available dependencies

test-dependencies:
  - tester@0.1.0 using test  # Globally available test dependencies

libraries:
  - name: foo
    path: libs/foo
    depends: [logger@0.1.0, app-maker@0.1.0]  # foo depends on these packages
    using: [gui]  # foo uses this library

  - name: bar
    path: libs/bar
    using: [foo]  # bar uses the internal library foo
```

While `foo` has access to `logger` and `gui`'s API, `bar` only has access to entities exposed by `foo`. However, both internal libraries have access to `printer` and `tester`'s `test` library.

## Docs

 [bpt's Library docs →](https://bpt.pizza/docs/latest/guide/libraries.html)
