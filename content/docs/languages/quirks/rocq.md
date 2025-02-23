---
weight: 50
---

# `rocq` layer

The `coq` layer enables support for the Coq proof assistant/programming
language via [Coqtail](https://github.com/whonore/Coqtail), which makes use of
[Coq LSP](https://github.com/ejgallego/coq-lsp) under the hood. Coqtail's
documentation specifies its requirements.

Tree-sitter support is currently not available.

## Bindings

Mappings are available [in the "Usage" section of Coqtail](https://github.com/whonore/Coqtail#usage)

## Configuration

Any vim **global** variable that [the "Configuration" section of Coqtail](https://github.com/whonore/Coqtail#configuration)
states can be set to configure Coqtail is also a valid field for this layer's
config, as long as you strip the `coqtail_` prefix.

As Coqtail handles the interaction with the underlying language server on its
own to provide some extra features, Neovim's LSP client doest not detect it.
Thus, the usual `lsp` and `lspconfig` fields should not be used.

## Examples

```lua
-- path/of/your/vim/config/init.lua

require("visimp")({
  rocq = {
    indent_on_dot = 1 -- do not use the coqtail_ prefix
  },
  languages = {
    "rocq"
  }
})
```

## Documentation

The full documentation for the plugin is available
[here](https://github.com/whonore/Coqtail/blob/main/doc/coqtail.txt).
