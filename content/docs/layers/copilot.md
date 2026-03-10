# `copilot` layer

The `copilot` layer allows you to use GitHub Copilot from within Neovim via the
official [copilot.vim](https://github.com/github/copilot.vim) plugin.

## Prerequisites
As of the time of writing, other than a GitHub account, the `copilot` layer requires 
Node.js and NPM to be installed on your system. 

## Configuration
Enable the `copilot` layer in your Visimp configuration:

```lua
-- path/of/your/vim/config/init.lua

require("visimp")({
  copilot = {},
})
```

Then, start Neovim and run `:Copilot setup` to install the plugin and follow
the instructions to authenticate with GitHub.
See [the official documentation](https://github.com/github/copilot.vim) for more details.

Any vim **global** variable that [the official documentation
](https://github.com/github/copilot.vim/blob/release/doc/copilot.txt) states can be
set to configure `copilot.vim` is also a valid field for this layer's config, as
long as you strip the `copilot_` prefix.

## Examples

```lua
-- path/of/your/vim/config/init.lua

require("visimp")({
  copilot = {
    filetypes = { -- do not use the copilot_ prefix
        xml = false, -- disable copilot for xml files
    },
  },
})
```
