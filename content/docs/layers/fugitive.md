---
title: "Fugitive (deprecated)"
---

# `fugitive` layer (deprecated)

The `fugitive` layer allows you to use git from within vim via the
[Fugitive](https://github.com/tpope/vim-fugitive) plugin. **It will be/was
deprecated in `visimp` v0.8.0 in favor of the [`neogit`]({{< ref
"/docs/layers/neogit" >}}) layer.**

## Bindings

When in Fugitive-specific buffers, several bindings can be used as documented
[here](https://github.com/tpope/vim-fugitive/blob/master/doc/fugitive.txt).


## Configuration

`visimp` does not manage Fugitive's configuration. It must be set via vimscript
global variables [specific to
Fugitive](https://github.com/tpope/vim-fugitive/blob/master/doc/fugitive.txt).

## Examples

```lua
-- path/of/your/vim/config/init.lua

require("visimp")({
  fugitive = {},
})
```

## Documentation

The full Fugitive documentation is available
[here](https://github.com/tpope/vim-fugitive).
