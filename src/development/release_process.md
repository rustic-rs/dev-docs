# Release Process

## CLI Releases: `rustic-rs` / `rustic_server` / `rustic_scheduler`

1. **Open a Release PR**: Open a [release PR workflow](https://github.com/rustic-rs/rustic/actions/workflows/release-pr.yml) by opening the drop down on the top right `Run workflow`.
For `Crate to release` select `rustic-rs` for `Version to release` select the version you want to release with the format `X.Y.Z` (strip the 'v').
This will create a PR with the changes needed to release the version.

1. **Auto-generate completions test fixtures**: If the CLI API tests fail, it means this is definitely a breaking change and needs a major/minor version bump. To update the fixtures, go to the top of the just created PR and copy the branch name, it should be in the form `release/rustic-rs/X.Y.Z`. Then go to the [update completions workflow](https://github.com/rustic-rs/rustic/actions/workflows/update-completions.yml). On the top right under `Run workflow`, run the workflow from the `main` branch and paste the just copied branch name to `PR branch to push to` and click `Run workflow`. This will auto-generate the completions test fixtures for the new version, to make the tests run through.

1. **Generate changelog**: To update the changelog, you need `git-cliff` installed. Run: `git-cliff -u -p .\CHANGELOG.md -t {new_version}`. This will update the changelog with the changes since the last tag.

1. **Documentation**: Check if the documentation needs to be updated somewhere. Take notes if there are any changes needed in the release process and update this document.

1. **Review and Merge the PR**: Review the PR and make sure all checks have passed. Then merge the PR.

1. **Tag the release**: After the PR has been merged, tag the commit on the `main` branch with the version number and push the tag to GitHub. This should make the release workflow run and crate a release for the tag and attach built artifacts to it. It will also copy the changelog to the release notes.

1. **Publishing to crates.io**: After pushing the tag to the `main` branch run `cargo publish` in the repository root.

1. **Publishing to GitHub**: After the release workflow has finished, go to the [releases page](https://github.com/rustic-rs/rustic/releases) and find your release draft with the attached artifacts. Edit the release draft to your liking and publish it.

1. **Write an announcement**: Write an announcement for the release and post it on the [rustic-rs/rustic discussions](https://github.com/rustic-rs/rustic/discussions/categories/announcements).

## Library Releases: `rustic_core` / `rustic_backend`

1. **Open a Release PR**: Open a [release PR workflow](https://github.com/rustic-rs/rustic_core/actions/workflows/release-pr.yml) by opening the drop down on the top right `Run workflow`.
For `Crate to release` select `rustic-rs` for `Version to release` select the version you want to release with the format `X.Y.Z` (strip the 'v').
This will create a PR with the changes needed to release the version.

1. **Auto-generate Public API test fixtures**: If the API tests fail, it means this is definitely a breaking change and needs a major/minor version bump. To update the fixtures, go to the top of the just created PR and copy the branch name, it should be in the form `release/rustic_core/X.Y.Z`. Then go to the [update completions workflow](https://github.com/rustic-rs/rustic_core/actions/workflows/update-public-api.yml). On the top right under `Run workflow`, run the workflow from the `main` branch and paste the just copied branch name to `PR branch to push to` and click `Run workflow`. This will auto-generate the Public API test fixtures for the new version, to make the tests run through.

1. **Examples**: Check if the examples need to be updated. Run documentation tests to check if the examples are still working. You can run them by running `cargo check --examples` in the `rustic_core` directory.

1. **Documentation**: Check if the documentation needs to be updated somewhere. Take notes if there are any changes needed in the release process and update this document. Run documentation tests to check if the documentation is still working. You can run them by running `cargo test --doc` in the `rustic_core` directory. You can also view the documentation with: `cargo doc --no-deps --all-features --document-private-items --open -p rustic_core`

1. **Generate changelog**: To update the changelog, you need `git-cliff` installed. Run: `git-cliff -u -p .\CHANGELOG.md -t {new_version}`. This will update the changelog with the changes since the last tag.

1. **Review and Merge the PR**: Review the PR and make sure all checks have passed. Then merge the PR.

1. **Tag the release**: After the PR has been merged, tag the commit on the `main` branch with the version number and push the tag to GitHub. This should make the release workflow run and crate a release for the tag. It will also copy the changelog to the release notes.

1. **Publishing to crates.io**: After pushing the tag to the `main` branch run `cargo publish` in the repository root.

1. **Review the Draft Release**: After the release workflow has finished, go to the [releases page](https://github.com/rustic-rs/rustic_core/releases) and find your release draft. Edit the release draft to your liking and publish it.

1. **Write an announcement**: Write an announcement for the release and post it on the [rustic-rs/rustic discussions](https://github.com/rustic-rs/rustic/discussions/categories/announcements).

<!-- TODO: Include `cargo smart-release` into the release process.

TODO:
<https://github.com/cargo-bins/cargo-binstall/blob/main/.github/workflows/release-pr.yml>
for implementing a release workflow based on a PR. -->
