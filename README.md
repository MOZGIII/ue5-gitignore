# ue4-gitignore

A correct `git` setup example *with `git-lfs`* for Unreal Engine 4 projects.

## Version Management Design and Conventions

This template implies some conventions to be used correctly, which are discussed below. You should be able copy and paste them into your project's `README.md` if you want to.

### Repo Structure

Repository structure is fixed, and it only has a few toplevel directores. Every other directory or file is ignored.

- `/Source`
- `/Config`
- `/Content`
- `/RawContent`

`git-lfs` management rules are mostly defined for file types, and not *paths*, however there can entire paths marked to be managed by `git-lfs`. Without a special note, expect only type-based rules apply to a directory.

#### `/Source`

C++ source code is stored under the `/Source` path. As with most other directories, this directory is managed by standard git (and not `git-lfs`). That means no blobs. Do not put here any `.dll`s, `.exe`s, `.zip`s and other binaries. Only text files are allowed.
Generated text files can reside in the local `/Source` dir, but should be ignored by git with additional entries in `.gitignore`.

#### `/Config`

Engine and game config files.

#### `/Content`

Game assets in Unreal Engine formats, `.uasset` and `.umap`. Only those two file types are allowed, everything else is ignored.

#### `/RawContent`

**This directory is managed entirely by `git-lfs`.**

`/RawContent` is a directory where you store assets in their source formats, in contrast to `/Content`, where assets are stored in the engine format (after the import). Having an asset in a source format is useful when you're still making updates to it. It may be a good idea to also have separate repos for managing work-in-progress assets (maybe in smaller collections or even idividually).

## How to use

1. Set up `git` and `git-lfs`.
2. Copy `.gitignore` and `.gitattributes` to your project.
3. Change the `Game.uproject` in `.gitignore` to your `.uproject` file name.

## Caveats

This setup does not include plugins support (so they would be ignored).
You'll have to change `.gitignore` accordingly to support them.
Pull requests are welcome! :wink:

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
