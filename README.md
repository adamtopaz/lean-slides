# Lean Slides

`Lean Slides` is a tool to 
automatically generate `reveal.js` slides 
from Markdown comments in the Lean editor.

![LeanSlides](https://github.com/0art0/lean-slides/assets/18333981/29029c7b-f586-45a1-b203-ffdc66a41049)

See `Demo.lean` for more details.

# Dependencies

`Lean Slides` works by combining together several tools:

- [`reveal.js`](https://revealjs.com/) (no install required)

- [`pandoc`](https://pandoc.org/)

- [`node.js`](https://nodejs.org/en)

- [`browser-sync`](https://browsersync.io/)

# Usage

To use `Lean Slides`, first install all the dependencies listed above.

`Lean Slides` can be added to an existing Lean repository
by inserting the following line in the `lakefile`:
```lean
require «lean-slides» from git "https://github.com/0art0/lean-slides"@"master"
```

---

In any file that imports `LeanSlides`, type

```lean
#slides +draft Test /-!
  <Markdown text>
-/
```

**Run `lake run lean-slides/serve-slides` from the command line
to start the HTTP server for the slides.**

Any slides that are not in draft mode should now be rendered.

The port used by `Lean Slides` can be modified through
an environment variable with the name `LEANSLIDES_PORT`.

# Features

`Lean Slides` turns comments written in the above format
into `reveal.js` slides which are rendered in the infoview
as a [`Widget`](https://github.com/EdAyers/ProofWidgets4).

The tool also features a code action to 
go in and out of draft mode.

The generated `reveal.js` slides
render mathematics by default
using `KaTeX`.
