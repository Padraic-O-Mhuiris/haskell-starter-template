# Haskell-Starter-Template

This project expects a system which is "nix-flake" compatible, you can read more about flakes [here](https://nixos.wiki/wiki/Flakes)

### Goal

This template is intended to be a "global dependency independent" environment for beginning haskell projects with modern text editors. It facilitates an all-encompassing declarative haskell development environment which defines explictly all tooling necessary, catered for that project, to get up and going. It is unneccessary to have any packages globally installed in your OS outside of `direnv` and `lorri`.

Admittedly, this setup targets a small set of developers as it may require only those who use nix, nix flakes and also possibly doom-emacs, but this may in the future expand

### Bootstrapping

First use the template to create a project via github or clone this repo - whatever is easiest

Using a one-time `nix-shell` command we can leverage the `cabal init` process to define what haskell project we would like

``` bash
nix-shell -p ghc cabal-install --run "cabal init -i"
```

It is also necessary to change the flake description and the default package the flake expects to build. There are two comments which should indicate where that is. The default package entry may vary depending on what sort of cabal project definition you have. It is based on IOHK's [haskell.nix](https://input-output-hk.github.io/haskell.nix/) for which more information may be specified there.

Lastly enable `direnv` integration by calling `direnv allow` which will jump into a development shell when a user enters that directory

``` bash
direnv allow
```

