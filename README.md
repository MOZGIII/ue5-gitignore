# ue5-gitignore

A correct `git` setup example _with [`git-lfs`](https://git-lfs.github.com/)_ for Unreal Engine 5 (and 4) projects.

## Version Management Design and Conventions

This template implies some conventions to be used correctly, which are discussed below. You should be able copy and paste them into your project's `README.md` if you want to.

### Repo Structure

Repository structure is fixed, and it only has a few toplevel directories. Every other directory or file is ignored.

- `/Source`
- `/Config`
- `/Plugins`
- `/Content`
- `/RawContent`

`git-lfs` management rules are mostly defined for file types, and not _paths_, however there can entire paths marked to be managed by `git-lfs`. Without a special note, expect only type-based rules apply to a directory.

#### `/Source`

C++ source code is stored under the `/Source` path. As with most other directories, this directory is managed by standard git (and not `git-lfs`). That means no blobs. Do not put here any `.dll`s, `.exe`s, `.zip`s and other binaries. Only text files are allowed.
Generated text files can reside in the local `/Source` dir, but should be ignored by git with additional entries in `.gitignore`.

#### `/Config`

Engine and game config files.

#### `/Plugins`

Game plugins. Every plugin lives in a subdirectory of the `/Plugins` dir. A plugin internal directory structure is not strictly documented, so there are no assumptions on how a plugin is structured.
It may be useful to use git submodules to manage plugins in a more robust manner.
It is expected that each plugin will have it's own `.gitignore` file in it's subdirectory, as well other required specific git tweaks.

#### `/Content`

Game assets in Unreal Engine formats, `.uasset` and `.umap`. Only those two file types are allowed, everything else is ignored.

#### `/RawContent`

**This directory is managed entirely by `git-lfs`.**

`/RawContent` is a directory where you store assets in their source formats, in contrast to `/Content`, where assets are stored in the engine format (after the import). Having an asset in a source format is useful when you're still making updates to it. It may be a good idea to also have separate repos for managing work-in-progress assets (maybe in smaller collections or even idividually).

## How to use

1. Set up `git` and `git-lfs`.
2. Copy `.gitignore` and `.gitattributes` to your project.

## Caveats

Take special care when working with plugins. Plugin structure is not very well defined, so you will be able to mess the git repo up with big files if you commit them to a plugin directory.

## Contributing

### Rules

This repo uses UNIX-style line endings and UTF-8.
Make sure every line in a text file is ended with a newline (especially the last line in a file, git should notify you if you've lost it). This is due to how lines are [defined](http://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap03.html#tag_03_206). Feel free to search the web for more info on why to end every file with an "empty line".

### How to contribute

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
