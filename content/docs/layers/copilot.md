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




