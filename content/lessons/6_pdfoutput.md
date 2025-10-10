---
numbering:
  title:
    offset: 0
  start: 7
---
(pdfoutput)=
# Create pdf output
FREEK

## Merits of pdf
FREEK

### Typst or pdf
FREEK

### Things to consider
FREEK

.gif -> create a png or jpg as well and use .*
videos, YT, interactive content are not supported -> created plugins


## Templates
FREEK


## Through GitHub actions or locally
RLANZAFAME



## Export to pdf

You can export your book to a pdf in two ways, with LaTeX or Typst.
Both methods have [advantages and disadvantages](https://mystmd.org/guide/creating-pdf-documents).

### Configure pdf output

We specified in the `myst.yml` file that we want to export to pdf using Typst.
You can also choose LaTeX.
See the `myst.yml` file, or [](#code_export) for the syntax.

:::{literalinclude} ../../myst.yml
:start-after: exports
:end-at: - id: output-pdf
:lineno-match:
:caption: Example of the export section in the `myst.yml` file.
:label: code_export
:::

You can specify the [output template](https://github.com/myst-templates).
We won't go into detail here, but you can find more information [in the MyST Markdown documentations](https://mystmd.org/guide/creating-pdf-documents).

### GitHub workflow

This template includes a GitHub workflow that automatically builds the pdf for you with Typst when you push changes.
Using the export options in `myst.yml`, a pdf will be built and committed to the `exports` directory when you push to GitHub.

```{note}
The GitHub workflow this only works when there are no errors in the markdown files.
For instance, it breaks when figures are missing.
```

### Local pdf build

If you have the Typst CLI installed, you can also build a pdf locally.

```console
myst build --typst
```

The book will be written to `exports/book.pdf`.
