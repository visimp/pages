---
weight: 50
---

# `rocq` layer

The `coq` layer enables support for the Coq proof assistant/programming
language via [Coqtail](https://github.com/whonore/Coqtail), whose requirements
are specified in the documentation. [Coq
LSP](https://github.com/ejgallego/coq-lsp) and Tree-sitter support are currently
not available.

## Bindings

Mappings are the same as the ones described [in the "Usage" section of
Coqtail](https://github.com/whonore/Coqtail#usage), with only one difference:
we use the `<leader>r` (`r` like Rocq) prefix, not `<leader>c`. This way, we
prevent some conflicts with [the default binds found in the `diagnostics`
layer]({{< relref "diagnostics#bindings" >}}). As described in the
[_Configuration_ section]({{< relref "#configuration" >}}), binds can be
freely overwritten by the user.

## Configuration

Since Coqtail handles the interaction with the underlying language server on its
own to provide some extra features, the Neovim's LSP client doest not detect it.
Thus, the usual `lsp` and `lspconfig` fields should not be used. Instead, the
layer provides the two following configuration fields:

- `coqtail` (defaults to `{nomap = 1, noimap = 1}`, as `visimp` default binds
  differ from Coqtail's): a table describing the settings to be used for
  `coqtail`. Any vim **global** variable that [the "Configuration" section of
  Coqtail](https://github.com/whonore/Coqtail#configuration) states can be set
  to configure Coqtail is also a valid field for `coqtail` table found in your
  `rocq` layer configuration, as long as you strip the `coqtail_` prefix;
- `binds` (defaults described in the [_Bindings_
  section]({{< relref "#bindings" >}})): bindings as would be passed to the
  [`binds` layer]({{< ref "binds" >}}).

## Examples

```lua
-- path/of/your/vim/config/init.lua

require("visimp")({
  rocq = {
    coqtail = {
      indent_on_dot = 1 -- do not use the coqtail_ prefixes
    },
    binds = {
      [{
        mode = 'n',
        bind = '<leader>l',
        opts = {
          desc = 'Rocq: check up to current line',
        },
      }] = vim_cmd_cb 'CoqToLine',
    },
  },
  languages = {
    "rocq"
  }
})
```

## Documentation

The full documentation for the plugin is available
[here](https://github.com/whonore/Coqtail/blob/main/doc/coqtail.txt).
