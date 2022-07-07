+++
title = "Adding Dependencies to a Project"
description = "Learn how to declare your project's dependencies."
date = 2022-07-06T08:00:00+00:00
updated = 2022-07-07T08:00:00+00:00
draft = false
weight = 40
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "Dependency resolution is one of the key goals of bpt. Dependencies take the form of external packages that your current project uses. In bpt, two kind of dependencies exist, regular dependencies that are used by your project and test dependencies used purely to test your project."
toc = true
top = false
+++

## Project Dependencies

In bpt, you're project can declare dependency on libraries from external packages. A dependency constist of the packages name, the range of accepted versions and libraries it uses. Dependencies are declared in the 'dependencies:' section of the `bpt.yaml` file.

<sup>Note<sup>1</sup>: Some packages don't contain libraries. In that case, the entire package is consider the library (e.g. below with 'fmt').</sup>

```yaml
# other package details above

dependencies:
  - fmt@8.1.1 # using fmt << Implicit
```

<sup>Note<sup>2</sup>: 'fmt' is part of bpt [default package](https://repo-3.bpt.pizza/) repo.</sup>

### Package Version Range

With bpt, you can specify the version range that you project accepts with different specifiers. Above you saw the `@` range specifier used, which indicates any version above the indicated one ('8.1.1' here) but below the next major version, i.e. [8.1.1, 9.0.0).

- `=1.2.3` - Indicates the exact version desired
- `~1.2.3` - Indicates the minimum version requirement and goes up to the next minor version change i.e. [1.2.3, 1.3.0)
- `^1.2.3` or `@1.2.3` - Indicates the minimum version requirement and goes up to the next major version change i.e. [1.2.3, 2.0.0)
- `+1.2.3` - Indicate the minumum version requirement and any higher version is acceptable

## Test Dependencies

Test dependencies are used exactly the same normal dependencies except they are not used by downstream users and they are declared in the 'test-dependencies:' section of the `bpt.yaml` file. Test dependencies are only used by files with the `*.test.cpp` extension i.e. they are only used for testing the project.

```yaml
# dependencies above

test-dependencies:
  - catch@2.13.9 using main
```

This allows use to have full access to catch2's testing facilities.

<sup>Note<sup>3</sup>: Notice the use of `using main` indicating we're using the 'main' library from catch2.</sup>

<sup>Note<sup>4</sup>: You still have to declare the header in the relevent files that use dependencies. Usually this follows th pattern of the package's/library's name and then the header name, e.g. `#include <catch2/catch.hpp>`</sup>

## Docs

[bpt's docs on dependencies →](https://bpt.pizza/docs/latest/guide/deps.html)
