---
weight: 50
---

# `lean` layer

The `lean` layer enables support for the lean proof assistant/programming
language via [lean.nvim](https://github.com/Julian/lean.nvim). Having Lean
installed is a prerequisite, as `leanls` is used as a language server by the
plugin under the hood.

Tree-sitter support is currently not available.

## Bindings

Mappings are listed [in the "Mappings" section of
lean.nvim](https://github.com/Julian/lean.nvim#mappings)

## Configuration

By default, `visimp` enables built-in abbreviations and mappings.
In general, every valid argument for `require('lean').setup` ([as shown
here](https://github.com/Julian/lean.nvim/wiki/Configuring-&-Extending))
is a valid configuration. For example, this method allows you to pass your
`leanls` server configuration as a value for the `lsp` field (beware: `visimp`
normally uses `lspconfig` for this). You could also pass `false` to disable the
language server. Unlike `visimp` language layers' usual `lsp` config field, you
may not specify a different executable name.

## Examples

```lua
-- path/of/your/vim/config/init.lua

require("visimp") {
  languages = {
    "lean" -- enable layer
  },
  lean = { -- configure layer
    abbreviations = {
        builtin = false -- disable builtin abbreviations
    },
    mappings = false, -- disable mappings
  }
}
```

## Documentation

The full documentation for the plugin is available
[here](https://github.com/whonore/Coqtail/blob/main/doc/coqtail.txt).
