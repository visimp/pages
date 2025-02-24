---
title: Idris
weight: 30
---

# `idris` layer

The `idris` layer enables support for the Idris programming
language via the [idris2-vim](https://github.com/edwinb/idris2-vim) mode (whose
documentation specifies the requirements) and the
[idris2-lsp](https://github.com/idris-community/idris2-lsp) language server.

Currently, there is no built-in support for Tree-sitter.

## Bindings

Mappings are available [in the "Interactive Editing Commands" section of
idris2-vim](https://github.com/edwinb/idris2-vim?tab=readme-ov-file#interactive-editing-commands).

## Configuration

Any vim **global** variable that [the "Configuration" section of
idris2-vim](https://github.com/edwinb/idris2-vim#configuration) states can be
set to configure idris2-vim is also a valid field for this layer's config, as
long as you strip the `idris_` prefix. As per usual, you may also use `lsp` and
`lspconfig` to configure the language server.

## Examples

```lua
-- path/of/your/vim/config/init.lua

require("visimp")({
  idris = {
    indent_if = 3 -- do not use the idris_ prefix
    lspconfig = {
      -- language server config
    }
  },
  languages = {
  "idris"
  }
})
```

## Documentation

The full documentation for the plugin is available
[here](https://github.com/edwinb/idris2-vim?tab=readme-ov-file). The plugin was
written by Idris designer [Edwin Brady](https://type-driven.org.uk/edwinb), who
also wrote [a blog post titled "Interactive Idris editing with
vim"](https://web.archive.org/web/20170307061942if_/http://edwinb.wordpress.com/2013/10/28/interactive-idris-editing-with-vim/).

The language server [is also
documented](https://github.com/idris-community/idris2-lsp/tree/main/doc).
