# homebrew-kalku

The Homebrew tap for [kalku](https://github.com/lnds/kalku): mutation
testing for humans, CI, and coding agents.

```sh
brew install lnds/kalku/kalku
```

It installs two binaries: `kalku`, and `kalku-kaikai`, the worker that
measures kaikai projects. Measuring an Elixir project also needs
[`kalku_elixir`](https://hex.pm/packages/kalku_elixir) as a test
dependency of that project.

macOS on Apple Silicon and Linux on x86_64: the platforms
[kaikai](https://github.com/lnds/kaikai) publishes a toolchain for, and
so the ones kalku can be built for at all.

## How the formula gets here

`Formula/kalku.rb` is not written by hand. kalku's release builds a
tarball on each platform's own runner, generates the formula from the
checksums of those exact files, and attaches it to the release;
`.github/workflows/update.yml` copies it here and, before committing,
downloads every url in it and checks the checksum matches. A formula
that names a tarball nobody can download is worse than no formula,
because the failure lands on a user's machine at install time.

Issues and pull requests belong in
[lnds/kalku](https://github.com/lnds/kalku).
