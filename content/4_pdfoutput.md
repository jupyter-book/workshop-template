# Export to pdf

You can export your book to a pdf in two ways: using LaTeX or Typst. Both have their advantages and disadvantages. For this template we made an automated GH action that builds the pdf for you utilizing Typst.

## Specify output in myst.yml

We specified in the `myst.yml` file that we want to export to pdf using Typst.
You can also choose LaTeX.
See the `myst.yml` file, or [](#code_export) for the syntax.

:::{literalinclude} ../myst.yml
:start-after: exports
:end-at: - id: output-pdf
:lineno-match:
:caption: Example of the export section in the `myst.yml` file.
:label: code_export
:::

Using the export option, a pdf will be generated in the `Exports` folder every time you push to GitHub. You can specify the [output template](https://github.com/myst-templates). We won't go into detail here, but you can find more information [here](https://mystmd.org/guide/creating-pdf-documents).

```{note}
We included a basic Typst book template  and a GitHub action that build the pdf. However, this only works when there are no errors in the markdown files. For instance, it breaks when figures are missing.
```
