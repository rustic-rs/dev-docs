# Release Process

## Common

1. Name your branch

   Use the following naming scheme for your branch:

   `release/{package-name}-vX.Y.Z` or `release/{package-name}-X.Y.Z`

   so the release branch for `rustic-rs` version `0.6.0` would be named:

   `release/rustic-rs-v0.1.0` or `release/rustic-rs-0.1.0` or
   `release/rustic-0.1.0`

## `rustic-rs`

1. CLI API

Run:

`mask completions test`

to check if the CLI API has changed and the version number needs to be bumped.

1. Version number

   Depending of the outcome of the CLI API check, bump the corresponding version
   number in `Cargo.toml`.

   Change the version number in the Readme as well.

1. Use the `release`-Branch

   Push the changes to a `release/vX.Y.Z` branch in the repository.

1. Changelog

   Update the `CHANGELOG.md` file.

   If `git-cliff` was used to generate the changelog, run:

   `git-cliff -l --exclude-path crates\rustic_core\* -o CHANGELOG.md -t {version}`

   otherwise, add the changes manually.

1. Documentation

   Check if the documentation needs to be updated somewhere. Take notes if there
   are any changes needed and update this document.

1. Test

   Update the test fixtures if needed. For example see the following.

1. CLI API Regenerate

   To generate the CLI API fixtures for the current version run:

   `mask completions regenerate`

   on Windows and one *Nix system to regenerate the CLI API fixtures for both
   platforms.

1. Examples

   Check if the examples need to be updated.

... TODO! ...

1. Publishing to crates.io

   Run:

   `cargo publish --manifest-path Cargo.toml`

## `rustic_core`

1. Public API

   Run:

   `mask public-api test`

   to check if the public API has changed and the version number needs to be
   bumped.

   Helpful advices are also given by the
   [Cargo reference](https://doc.rust-lang.org/cargo/reference/semver.html).

1. Version number

   Depending of the outcome of the Public API check, bump the corresponding
   version number in `rustic_core/Cargo.toml`.

   Change the version number in the Readme as well.

1. Use the `release`-Branch

   Push the changes to a `release/vX.Y.Z` branch in the repository

1. Changelog

   Update the `CHANGELOG.md` file.

   If `git-cliff` was used to generate the changelog, run:

   `git-cliff -l --include-path crates\rustic_core\* -o .\crates\rustic_core\CHANGELOG.md -t {version}`

   otherwise, add the changes manually.

1. Documentation

   Check if the documentation needs to be updated somewhere. Take notes if there
   are any changes needed and update this document.

1. Tests

   Update the test fixtures if needed. For example see the following.

1. Examples

   Check if the examples need to be updated.

... TODO! ...

1. Public API Regenerate

   To generate the public API fixtures for the current version run:

   `mask public-api regenerate`

   on Windows and one *Nix system to regenerate the public API fixtures for both
   platforms.

1. Publishing to crates.io

   Run:

   `cargo publish --manifest-path crates/rustic_core/Cargo.toml`

## After release

<!-- TODO: Include `cargo smart-release` into the release process.

TODO:
<https://github.com/cargo-bins/cargo-binstall/blob/main/.github/workflows/release-pr.yml>
for implementing a release workflow based on a PR. -->
