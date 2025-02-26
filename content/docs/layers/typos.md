# `typos` layer

The `typos` layer provides [`typos-lsp`](https://github.com/tekumara/typos-lsp),
a spell checker for source code.

This is different from the [`ltex` layer]({{< ref "/docs/layers/ltex" >}}),
which provides a grammar checker for natural languages (i.e., prose in Typst,
$\LaTeX$, Markdown...).

|             | `ltex`                   | `typos`               |
|-------------|--------------------------|-----------------------|
| Languages   | Natural languages        | Programming languages |
| Checks      | Spelling, grammar, style | Spelling              |
| Performance | Fast                     | Faster                |

Actually, `typos` also runs on content in natural language by default, as that
cannot hurt.

## Configuration

All configuration is done [via config
files](https://github.com/tekumara/typos-lsp#config-file-support), rather than
the layer itself.

## Examples

```lua
-- path/of/your/vim/config/init.lua

require("visimp")({
  typos = {},
})
```

## Documentation

The official documentation for the underlying plugin is available at the
project's [homepage](https://github.com/tekumara/typos-lsp).
