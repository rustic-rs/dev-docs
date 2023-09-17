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
