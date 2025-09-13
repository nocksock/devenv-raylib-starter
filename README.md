# Devenv Starter for Raylib

Currently only configured for macOS, but adjusting for linux should be trivial.
PRs welcome.

## Dependencies

- [devenv](https://devenv.sh/getting-started/)
- [direnv](https://direnv.net/) for [automatic shell activation]

Devenv will handle everything else.

## Commands

- `dev-build`: build
- `dev-run`: build and run

Both can take a filename as argument, eg.: `dev-run test.c`, and will default to `main.c` if none given.

They work in any directory within the devenv shell.

## Using with neovim 

tip: If you started `nvim` from within the devenv shell, then you can quickly
build and run using `:!dev-run`.

### LSP Config

This devenv includes `clangd`.

This is what I currently have in [my config]

```lua
require "lspconfig".clangd.setup({
  cmd = { "clangd", "--background-index", "--clang-tidy" },
  init_options = {
    clangdFileStatus = true
  },
})
```

[my config]: https://github.com/nocksock/dotfiles/blob/main/nvim/after/plugin/lsp/clangd.lua
[automatic shell activation]: https://devenv.sh/automatic-shell-activation/
