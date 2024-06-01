# Development guide

Work in progress ...

## `cargo xtask`

We utilize `cargo xtask` to provide additional functionality for the development
process.

### Usage

Currently it supports the following functionalities:

| Command                    | Description                                                       |
| -------------------------- | ----------------------------------------------------------------- |
| `cargo xtask help`         | Show an overview over all or the help of the given subcommand(s). |
| `cargo xtask bloat-deps`   | Show biggest crates in release build using cargo-bloat.           |
| `cargo xtask bloat-time`   | Show longest times taken in release build using cargo-bloat.      |
| `cargo xtask coverage`     | Generate code coverage report.                                    |
| `cargo xtask install-deps` | Install dependencies for the development process.                 |
| `cargo xtask timings`      | Show longest times taken in release build using cargo-bloat.      |

## Maskfile

We utilize `mask` to provide additional functionality for the development
process.

### Installation

Install `mask` with:

```bash
cargo install mask
```

or by using [`scoop`](https://scoop.sh/):

```bash
scoop install mask
```

### Usage

A maskfile is self-documenting, because it is written in Markdown. You can view
the maskfile [here](https://github.com/rustic-rs/rustic/blob/main/maskfile.md).

## Dockerfile technical reference

We utilize multistage docker build with following stages

- `chef` - utility step to shorten code
- `planner` - analyze the current project to determine the minimum subset of
  files (`Cargo.lock` and `Cargo.toml` manifests) required to build it
- `builder` - consists of 2 container layers
  - first - contains build dependencies (it wii be rebuild only if Cargo.lock or
    Cargo.toml has changes)
  - second - main build of our application
- `runtime` - debian slim image for running our app (we don't use alpine cause
  [this](https://web.archive.org/web/20231214004214/https://andygrove.io/2020/05/why-musl-extremely-slow/))

### `cargo-chef`

We utilize `chef` to cache the dependencies of Rust project and speed up Docker
builds.

#### Installation

Locally

```bash
cargo install cargo-chef --locked
```

Dockerfile

```bash
FROM lukemathwalker/cargo-chef:latest-rust-1.70.0 AS chef
```

#### Usage

In Dockerfile we used `ARG` to lock `rust` version. (By default = `1.70.0`).

When `rust` version is updated, you need to either update the standard version

```bash
ARG RUST_VERSION=1.70.0
```

or use the build argument

```bash
docker build --build-arg="RUST_VERSION=1.70.0" .
```
