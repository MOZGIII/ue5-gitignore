# ue4-gitignore

A correct `git` setup example *with `git-lfs`* for Unreal Engine 4 projects.

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
