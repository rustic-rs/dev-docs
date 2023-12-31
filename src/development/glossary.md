# Glossary

## Table of Contents

- [Archiver](#archiver)
- [Backend](#backend)
- [Beta Builds](#beta-builds)
- [Blob](#blob)
- [Cache](#cache)
- [Chunker](#chunker)
- [Cold Repository](#cold-repository)
- [Completions](#completions)
- [Compression](#compression)
- [Data Pack](#data-pack)
- [Description](#description)
- [Environmental Variables](#environmental-variables)
- [Filter](#filter)
- [Glob](#glob)
- [Hot Repository](#hot-repository)
- [Library (rustic)](#library-rustic)
- [Labels and Tags](#labels-and-tags)
- [Nodes](#nodes)
- [One-File-System](#one-file-system)
- [Pack and Pack Size](#pack-and-pack-size)
- [Packer](#packer)
- [Parallelization](#parallelization)
- [Parent](#parent)
- [Profiles and Configs](#profiles-and-configs)
- [Repository](#repository)
- [Repack](#repack)
- [Retry](#retry)
- [Scripting](#scripting)
- [Snapshot](#snapshot)
- [Source](#source)
- [Sub-trees](#sub-trees)
- [Storage ID](#storage-id)
- [Trees](#trees)
- [Warm-up](#warm-up)

### Archiver

**Note**: This content is still under review/in progress.

An archiver is a tool or software that creates archives, which are collections
of files and data bundled together.

### Backend

**Note**: This content is still under review/in progress.

The backend refers to the server-side of a software application. It is
responsible for processing requests from the frontend, handling data storage,
and executing complex tasks.

### Beta Builds

Beta builds are pre-release versions of the software made available to a limited
audience for testing and feedback before the official release. They are used to
identify and fix bugs and gather user input. Beta-builds of `rustic` can be
found in the [rustic-beta](https://github.com/rustic-rs/rustic-beta) repository.

### Blob

A Blob combines a number of data bytes with identifying information like the
SHA-256 hash of the data and its length.

### Cache

**Note**: This content is still under review/in progress.

A cache is a temporary storage mechanism used to store frequently accessed data.
It helps to speed up operations and reduce the need for repetitive computations.

### Chunker

**Note**: This content is still under review/in progress.

The chunker is a component responsible for breaking down data into smaller,
manageable pieces or chunks, typically for more efficient processing and
storage.

### Cold Repository

**Note**: This content is still under review/in progress.

The term cold repository refers to a storage location for data that is less
frequently accessed and may require extra steps to retrieve.

### Completions

Completions refer to the suggestions or options provided by the terminal to help
users complete commands or input based on what they have typed so far. You can
generate completions using `rustic completions <SH>` where `<SH>` is one of
`bash, fish, zsh, powershell`. More information on shell completions you can
find in the [FAQ](https://rustic.cli.rs/docs/commands/misc/completions.html).

### Compression

Compression is the process of reducing the size of data or files to save storage
space and improve transfer speeds.

### Data Pack

**Note**: This content is still under review/in progress.

A data pack is a collection of data files bundled together for distribution or
deployment.

### Description

**Note**: This content is still under review/in progress.

A description is metadata that provides additional information or context about
an item within the project.

### Environmental Variables

Environmental variables are settings or values that affect the behavior of
software running on a particular system. They provide configuration and runtime
information. Available settings that are influenced by environment variables can
be found [here](https://github.com/rustic-rs/rustic/blob/main/config/README.md).

### Filter

A filter is used to selectively process or display certain data while excluding
the rest based on specific criteria. It helps to narrow down relevant
information. `rustic` integrates the [Rhai](https://rhai.rs/) scripting language
for snapshot filtering. `--filter-fn`` allows to implement your own snapshot
filter in a 'Rust-like' syntax
([Rust closure](https://doc.rust-lang.org/book/ch13-01-closures.html)).

### Glob

A glob is a pattern used to match and select files or directories based on
specific rules. It is commonly used for file manipulation and searching.

### Hot Repository

**Note**: This content is still under review/in progress.

The term hot repository refers to a storage location for data that is readily
available for access and immediate use.

### Library (rustic)

In the context of `rustic`, a library refers to a set of reusable code
components that can be used by other parts of the project or by external
projects. The main library being used is `rustic_core`. The crate resides in
[`crates/rustic_core/`](https://github.com/rustic-rs/rustic/tree/main/crates/rustic_core).
You can use it in your project with `cargo add rustic_core`.

### Labels and Tags

Labels, tags, and descriptions are metadata elements used to categorize and
annotate items within the project. They provide context and make it easier to
search and manage repositories.

### Nodes

**Note**: This content is still under review/in progress.

Nodes are individual elements within a hierarchical structure, such as trees or
sub-trees.

### One-File-System

**Note**: This content is still under review/in progress.

One-File-System is a mode or option that restricts file operations to a single
filesystem, preventing access to other filesystems on the system.

### Pack and Pack Size

A Pack combines one or more Blobs, e.g. in a single file. In this project,
packing refers to the process of combining multiple files or data into a single
pack. Pack size refers to the size of such packages.

### Packer

The packer is a component responsible for combining multiple [Blobs](#blob) into
packs.

### Parallelization

Parallelization is the technique of dividing tasks into smaller units and
executing them simultaneously on multiple processors or cores to achieve faster
performance.

### Parent

**Note**: This content is still under review/in progress.

In this project, a parent refers to a higher-level element or entity that has
one or more subordinate components or children associated with it.

### Profiles and Configs

Profiles and configurations are settings that determine the behavior of the
application based on different scenarios or environments. They allow the project
to adapt to varying conditions. A profile consists of a set of configurations.
More information on profiles and configuration options can be found
[here](https://github.com/rustic-rs/rustic/tree/main/config#profiles).

### Repository

A repository is often abbreviated as "repo". All data produced during a backup
is sent to and stored in a repository in a structured form, for example in a
file system hierarchy with several subdirectories. It is a version-controlled
storage location for backups. It allows multiple snapshots to be stored, tracks
changes, manages the history of files and directories, and is able to list its
contents.

### Repack

**Note**: This content is still under review/in progress.

Repack refers to the process of recreating a package or archive, often with some
changes or updates.

### Retry

Retry is the act of attempting an operation again if it previously failed. It is
a common approach to handle temporary errors or network issues.

### Scripting

Scripting refers to the use of scripts, which are small programs written in a
scripting language, to automate tasks or execute specific operations. `rustic`
integrates the [Rhai](https://rhai.rs/) scripting language for snapshot
filtering. `--filter-fn`` allows to implement your own snapshot filter in a
'Rust-like' syntax
([Rust closure](https://doc.rust-lang.org/book/ch13-01-closures.html)).

### Snapshot

A Snapshot stands for the state of a file or directory that has been backed up
at some point in time. The state here means the content and metadata like the
name and modification time for the file or the directory and its contents.

### Source

**Note**: This content is still under review/in progress.

In the context of this project, the source refers to the backup sources `rustic`
is taking snapshots of.

### Sub-trees

**Note**: This content is still under review/in progress.

Sub-trees are lower-level hierarchical structures that are part of a larger
hierarchical structure, such as trees.

### Storage ID

A storage ID is the SHA-256 hash of the content stored in the repository. This
ID is required in order to load the file from the repository.

### Trees

**Note**: This content is still under review/in progress.

Trees are hierarchical structures that organize data with a root node and
branches (sub-trees) leading to leaves.

### Warm-up

**Note**: This content is still under review/in progress.

Warm-up is the process of preparing a system or a component for optimal
performance. It involves loading necessary data into memory or initializing
resources beforehand to reduce startup time.
