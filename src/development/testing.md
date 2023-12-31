# Testing

## Completions (CLI-API)

### Generate completions fixtures

In the repository root run:

`cargo run -- completions {SHELL} > tests/completions-fixtures/{SHELL}.txt`

with `{SHELL}` being one of `bash`, `fish`, `zsh`, or `powershell`.

### Test completions

Run the test with:

`cargo test --test completions -- --ignored`

## Code coverage

### VS-Code/VS-Codium Extension

You can live preview the coverage on your code with this extension:

```text
Name: Coverage Gutters
Id: ryanluker.vscode-coverage-gutters
Description: Display test coverage generated by lcov or xml - works with many languages
Version: 2.11.0 (at the time of writing)
Publisher: ryanluker
VS Marketplace Link: <https://marketplace.visualstudio.com/items?itemName=ryanluker.vscode-coverage-gutters>
```

### Generate with `cargo-tarpaulin`

Install cargo tarpaulin `cargo install cargo-tarpaulin` and run in the
repository root:

`cargo tarpaulin --all -o Lcov --output-dir ./coverage`

### Generate with `grcov`

Install the dependencies for code coverage:

`cargo xtask install-deps code-coverage`

Generate a code coverage report into the `/coverage` directory:

`cargo xtask coverage`
