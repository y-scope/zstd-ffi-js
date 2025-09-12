# Building the project

This document explains how to build the project.

## Requirements
* CMake 3.16 or higher
* GNU Make
* Python 3
* [Task] 3.40.0 or higher

## Setup

Initialize and update submodules:

```shell
git submodule update --init --recursive
```

## Build zstd-wasm

To build the zstd-wasm library:

```shell
task zstd-wasm
```

The task first runs `:deps:download-zstd` to fetch the latest Zstandard source code, then executes
`:deps:install-zstd-single-file` to produce the single-file library. Finally, it builds the CMake
project, which uses Emscripten to expose the bindings to JavaScript.

To clean the build:

```shell
task clean-zstd-wasm
```

### Supported Environments

The build system generates separate binaries for different JavaScript environments:
- Node.js
- Web Workers

[Task]: https://taskfile.dev
