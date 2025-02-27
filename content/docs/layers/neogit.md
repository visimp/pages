# `neogit` layer

The `neogit` layer allows you to use git from within as a Neovim TUI via the
[Neogit](https://github.com/NeogitOrg/neogit) plugin.

## Bindings

When in Neogit-specific buffers, several bindings can be used as documented in
[the default configuration](https://github.com/NeogitOrg/neogit#configuration).


## Configuration

Any valid configuration for Neogit as documented
[here](https://github.com/NeogitOrg/neogit#configuration) is a valid
configuration for this layer.

## Examples

```lua
-- path/of/your/vim/config/init.lua

require("visimp")({
  neogit = {
    graph_style = "ascii",
    git_services = {
      ["codeberg.org"] = "https://codeberg.org/${owner}/${repository}/compare/${branch_name}?expand=1",
    },
    initial_branch_name = "feat/",
    signs = {
      hunk = { "󰍟", "󰍝" },
      item = { "󰍟", "󰍝" },
      section = { "󰍟", "󰍝" },
    },
    integrations = {
      telescope = true,
      diffview = true,
    },
  },
})
```

## Documentation

The full Neogit documentation is available
[here](https://github.com/NeogitOrg/neogit/blob/master/doc/neogit.txt).
