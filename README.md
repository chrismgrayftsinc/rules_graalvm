# `rules_graalvm`

> [!IMPORTANT]  
> Currently in beta. Will probably break

Use [GraalVM](https://graalvm.org) from Bazel, with support for:

- [Building native image binaries](./docs/native-image.md)
- [Installing components with `gu`](./docs/components.md)
- [Using GraalVM as a Bazel Java toolchain](./docs/toolchain.md)
- [Support for Bazel 6, Bazel 7, and Bzlmod](./docs/modern-bazel.md)
- Support for macOS, Linux, Windows
- Support for latest modern GraalVM releases (Community Edition and Oracle GraalVM)

## Installation

**Via `WORKSPACE`:**
```starlark
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_graalvm",
    sha256 = "<sha256 sum>",
    strip_prefix = "rules_graalvm-<commit>",
    urls = [
        "https://github.com/sgammon/rules_graalvm/archive/<commit>.tar.gz",
    ],
)

load("@rules_graalvm//graalvm:repositories.bzl", "graalvm_repository")

graalvm_repository(
    name = "graalvm",         # anything you want
    version = "20.0.2",       # exact version of a GraalVM CE or Oracle GVM release
    distribution = "oracle",  # required for newer GVM releases (`oracle`, `ce`, or `community`)
    java_version = "20",      # java language version to use/declare
)
```

**Via `MODULE.bazel`:**
```starlark
# Coming soon.
```

## Usage: Java Toolchains

You can use the `graalvm_repository` as a Java toolchain, by registering it like below:

**In `WORKSPACE.bazel`:**
```starlark
# Coming soon.
```

**Or, in a `.bazelrc` file:**
```
# Coming soon.
```

## Usage: Build a native binary

**In a `BUILD.bazel` file:**
```python
load("@rules_java//java:defs.bzl", "java_library")
load("@rules_graalvm//graalvm:defs.bzl", "native_image")

java_library(
    name = "main",
    srcs = glob(["Main.java"]),
)

native_image(
    name = "main-native",
    deps = [":main"],
    main_class = "Main",
)
```

## Acknowledgements

Built on top of @andyscott's fantastic work with [rules_graal](https://github.com/andyscott/rules_graal).
