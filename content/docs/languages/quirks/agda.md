---
weight: 10
---

# `agda` layer

The `agda` layer enables support for the Agda proof assistant/programming
language. This is achieved by using the official [Agda Language
Server](https://hackage.haskell.org/package/agda-language-server) and
the [Cornelis plugin](https://github.com/agda/cornelis)
(i.e., [agda-mode aka Emacs
mode](https://agda.readthedocs.io/en/latest/tools/emacs-mode.html), but for
Neovim). The latter requires
[`stack`](https://docs.haskellstack.org/en/stable/install_and_upgrade/).

## Bindings

Some default bindings are provided for Cornelis. They are the same as the ones
specified in [Cornelis's example
configuration](https://github.com/agda/cornelis#example-configuration). In
normal mode:

- `<leader>l` **loads** and type-checks the buffer;
- `<leader>r` **refines** the goal;
- `<leader>d` performs a case **distinction**/split;
- `<leader>,` shows goal type and context;
- `<leader>.` shows inferred type of hole contents;
- `<leader>n` solves constraints;
- `<leader>a` performs an **automatic** proof search;
- `gd` **goes** to **definition**;
- `[/` jumps to previous goal;
- `/]` jumps to next goal;
- `<C-A>` is like `agda-mode`'s `<C-A>`, but also targets sub/super-scripts;
- `<C-X>` is like `agda-mode`'s `<C-X>`, but also targets sub/super-scripts.

## Configuration

Any vim **global** variable mentioned in [the "Configuration" section of
Cornelis](https://github.com/agda/cornelis#configuring-cornelis-behavior)
is also a valid field for this layer's config, as long as you strip the
`cornelis_` prefix.

## Examples

```lua
-- path/of/your/vim/config/init.lua

require("visimp")({
  agda = {
    max_size = 30 -- do not use the cornelis_ prefix for Cornelis settings
    lspconfig = {
      -- your Agda Language Server config
    }
  },
  languages = {
    "agda"
  }
})
```

## Documentation

- [language
  server](https://github.com/agda/cornelis#configuring-cornelis-behavior);
- [Cornelis](https://github.com/agda/cornelis).
