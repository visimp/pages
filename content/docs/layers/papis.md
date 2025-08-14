# `papis` layer

The `papis` layer offers integration with the [Papis bibliography
manager](https://papis.readthedocs.io/en/latest/) via the
[`papis.nvim`](https://papis.readthedocs.io/en/latest/) plugin.

You need to install `yq` and the development files for `sqlite`. `visimp` will
take care of the rest.

## Bindings

Although bindings are disabled by default, several bindings can be used as
documented by [`papis.nvim`](https://github.com/jghauser/`papis.nvim`#keymaps).

## Configuration

Any [valid configuration for
`papis.nvim`](https://github.com/jghauser/papis.nvim#setup) is a valid
configuration for this layer. If you do not specify a value for
`init_filetypes`, `visimp` will try to infer one based on the [language
layers](../language) you have enabled.

## Examples

```lua
-- path/of/your/vim/config/init.lua

require("visimp")({
  papis = {
    enable_keymaps = true,
  },
})
```

## Documentation

The full Neogit documentation is [also
available](https://github.com/jghauser/papis.nvim/blob/main/doc/papis.txt).
