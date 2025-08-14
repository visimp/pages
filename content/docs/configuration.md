---
title: Configuration
weight: 30
---

# Configuration

## Configuring `visimp`

You can configure your `visimp` installation from neovim's `init.lua` located
under your `$XDG_CONFIG_DIR/nvim`:

```lua
require 'visimp' {
  -- my (empty) visimp configuration
}
```

Requiring the `visimp` script returns a "setup" function. This procedure
is invoked by passing a description of your intended `visimp` configuration as
parameter. In the example above, we are using an empty object (`{}`) as our
configuration, so no layer is enabled, besides the default ones. If you want
to enable one, use its name as a new key (whose value will be an empty object
for now). The available layers are listed at [the bottom of this
page]({{< relref "#standard-layers" >}}). The following configuration enables the
`autopairs`, `gitsigns`, and `outline` layers:

```lua
require 'visimp' {
  autopairs = {},
  gitsigns = {},
  outline = {}
}
```

To disable a layer, you can either remove it from your configuration or use
`false` as its value. The latter is needed when the layer is enabled by default:

```lua
require 'visimp' {
  gitsigns = false, -- "gitsigns" is disabled: you may as well remove its entry
  
  lsp = false,      -- this line, on the contrary, is required as the layer
                    -- would be enabled by default
}
```

So far, we've stuck to empty objects as values for our enabled layers. These
objects actually represent your configuration for that specific layer. Usually,
each key is one of the settings available for the layer in question:

```lua
require 'visimp' {
  defaults = {             -- The "defaults" layer is enabled and should use:
    foldmethod = 'marker', -- - "marker" as its "foldmethod"
    tabsize = 4            -- - 4 as its "tabsize"
  }
}
```

When a setting isn't specified, its default value is used, and every setting has
a default value, so `{}` is always an acceptable configuration. Actually, some
layers accept a list of values instead of a key-value pairs configuration. The
main exception is the `languages` meta-layer:

```lua
require 'visimp' {
  languages = { -- accepts a list of languages for which support is needed.
    'c',
    'go',
    'latex',
    'rust'
  }
}
```

We refer to language-agnostic layers as "standard". They are listed below. If
you are interested in layers providing support for a specific language, you can
check the [list of supported languages]({{< ref "/docs/languages/supported-languages" >}}) instead.

## Standard Layers

Before configuring a new standard layer, you're advised to take a look at its
reference page. You can look it up in the following table.

| Layer name                                                | Short description                                                          | Default |
| --------------------------------------------------------- | -------------------------------------------------------------------------- | :-----: |
| [`autopairs`]({{< ref "/docs/layers/autopairs" >}})       | Automatic completion of `{`, `(`, and HTML tags                            |         |
| [`binds`]({{< ref "/docs/layers/binds" >}})               | Custom bindings for native Vim commands                                    |         |
| [`blankline`]({{< ref "/docs/layers/blankline" >}})       | Indentation guides                                                         |         |
| [`cmp`]({{< ref "/docs/layers/cmp" >}})                   | Completion engine                                                          | ☆       |
| [`colorizer`]({{< ref "/docs/layers/colorizer" >}})       | Color highlighter                                                          |         |
| [`defaults`]({{< ref "/docs/layers/defaults" >}})         | Customizable sane defaults                                                 | ☆       |
| [`diagnostics`]({{< ref "/docs/layers/diagnostics" >}})   | Pretty list of diagnostics, quickfixes, and more                           |         |
| [`fugitive`]({{< ref "/docs/layers/fugitive" >}})         | Git wrapper                                                                |         |
| [`gitsigns`]({{< ref "/docs/layers/gitsigns" >}})         | Git code decorations                                                       |         |
| [`greeter`]({{< ref "/docs/layers/greeter" >}})           | Custom Nvim greeter                                                        | ☆       |
| [`icons`]({{< ref "/docs/layers/icons" >}})               | Adds file type icons                                                       |         |
| [`languages`]({{< ref "/docs/layers/languages" >}})       | Enable [language layers]({{<ref "/docs/languages/supported-languages" >}}) | ☆       |
| [`lsp`]({{< ref "/docs/layers/lsp" >}})                   | Manager for Neovim's LSP client and LSP servers                            | ☆       |
| [`lspformat`]({{< ref "/docs/layers/lspformat" >}})       | Formatting on save via LSP                                                 | ☆       |
| [`lspsignature`]({{< ref "/docs/layers/lspsignature" >}}) | Function signatures as you type                                            | ☆       |
| [`ltex`]({{< ref "/docs/layers/ltex" >}})                 | Grammar checking on natural language prose                                 |         |
| [`neogit`]({{< ref "/docs/layers/neogit" >}})             | Git wrapper                                                                |         |
| [`nvimtree`]({{< ref "/docs/layers/nvimtree" >}})         | File explorer tree                                                         |         |
| [`papis`]({{< ref "/docs/layers/papis" >}})               | Bibliography management via Papis                                          |         |
| [`rainbow`]({{< ref "/docs/layers/rainbow" >}})           | Rainbow parenthesis via Tree-sitter                                        | ☆       |
| [`snippet`]({{< ref "/docs/layers/snippet" >}})           | Code snippets engine                                                       | ☆       |
| [`statusline`]({{< ref "/docs/layers/statusline" >}})     | Customizable status line                                                   | ☆       |
| [`telescope`]({{< ref "/docs/layers/telescope" >}})       | Fuzzy finder and related features                                          | ☆       |
| [`theme`]({{< ref "/docs/layers/theme" >}})               | Install and enable classic vim themes                                      | ☆       |
| [`treesitter`]({{< ref "/docs/layers/treesitter" >}})     | Syntax highlighting                                                        | ☆       |
| [`typos`]({{< ref "/docs/layers/typos" >}})               | Source code spellchecker                                                   |         |
| [`whichkey`]({{< ref "/docs/layers/whichkey" >}})         | Popups for key bindings suggestions                                        |         |
| [`zen`]({{< ref "/docs/layers/zen" >}})                   | Distraction-free "zen" mode                                                |         |

### Deprecated standard layers


| Layer name                                                | Short description                                 |
| --------------------------------------------------------- | ------------------------------------------------- |
| ~~[`comment`]({{< ref "/docs/layers/comment" >}})~~       | ~~Automatic (un)commenting support~~              |
| ~~[`fugitive`]({{< ref "/docs/layers/fugitive" >}})~~     | ~~Git wrapper~~                                   |
| ~~[`outline`]({{< ref "/docs/layers/outline" >}})~~       | ~~Buffer outline as a tree-like view of symbols~~ |
