---
weight: 10
---

# Guidelines

Thanks for considering helping us out! This page lists the steps required to
contribute to the `visimp` project.

## Discussing your contribution

Whether you are working on a new feature or fixing a bug, get in touch with the
project maintainers via the issue tracker. Please discuss the details of your
contribution together and make sure they are happy with it. This way, you will
not waste time on contributions that will be rejected.

## Reading the documentation

Before starting to work on your contribution, make sure you have read the
[Introduction]({{< ref "/docs/introduction" >}}), [Configuration]({{< ref
"/docs/configuration" >}}), and [Layer]({{< ref "layer" >}}) sections.

## Writing code

Depending on which part of the codebase you are working on, you might need to
take different extra steps.

### Working on internals

Update the [Introduction]({{< ref "/docs/introduction" >}}),
[Configuration]({{< ref "/docs/configuration" >}}), and [Layer]({{< ref "layer"
>}}) pages, if necessary.

### Working on a standard layer

When editing/adding a standard (i.e., non-language) layer, make sure the
respective documentation in `docs/layers` is up-to-date and referenced in the
corresponding table in [Configuration]({{< ref "/docs/configuration" >}}).

### Working on a language layer

When editing/adding a language layer, make sure it is listed in the
corresponding table in [Supported languages]({{< ref
"/docs/languages/supported-languages" >}}). If your language layer includes
peculiar features specific to said language's platform (e.g., `idris`, `lean`,
`rocq`), the entry in the table should also link to a dedicated documentation
page in `docs/languages/quirks/`.

In general, your language layer should provide a Tree-sitter grammar. You can
look for one in the list of [`nvim-treesitter` supported
languages](https://github.com/nvim-treesitter/nvim-treesitter#supported-languages).
It should also provide a language server installable via Mason. You can look for
one on [Mason's package list](https://mason-registry.dev/registry/list). Make
sure this language server is [supported by
`nvim-lspconfig`](https://github.com/neovim/nvim-lspconfig/blob/master/doc/server_configurations.md).

If your language layer's configuration does not have precisely two fields `lsp`
and `lspconfig`(the default behavior when creating a new language layer),
document so in [the Configuration section of the Languages page]({{< ref
"/docs/layers/languages#configuration" >}}).

Make sure your language is listed in the sample configuration found in
`_init.lua`.

## Documenting your contribution

Two types of documentation must be provided:

- every Lua function or field must be annotated through
  [LuaCATS](https://luals.github.io/wiki/annotations/). The Lua Language Server
  supports this already;
- the main documentation is available at
  [`visimp/pages`](https://github.com/visimp/pages).

All tables and list in the documentation and in the sample configuration at
`_init.lua` should be presented in alphabetical order. Capitals letters should
be used uniformly. Please especially mind the capitalizations of "`visimp`"
(which is to be always monospaced) and "Tree-sitter".

## Final checks

Ensure the [Lua Language Server](https://luals.github.io/) is not emitting any
warnings. Then, before submitting your contribution, please run the following
from the project's root directory:

```bash
# Format

stylua .

# Lint

"${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/mason/bin/lua-language-server --check .
luacheck .

# Spellcheck

typos .
```

If your work is not properly formatted, contains linter warnings/error, or
English spelling errors, the respective automated tests will fail on your pull
request.
