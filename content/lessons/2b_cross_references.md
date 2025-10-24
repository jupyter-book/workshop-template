---
numbering:
  title:
    offset: 1
---

# Cross-references

MyST has strong support for referencing, with many links having dynamic, interactive tooltips.
These features help to more seamlessly share data between MyST projects and other internet resources.
Review the [references section of the cheat sheet](#cheatsheet-ref) for a reminder of the syntax.

## Labels

:::{exercise} Labels
Add a label to this paragraph.

And reference it [here]().
:::

## Referencing MyST projects

The [MyST guide](xref:myst-guide) has already been added as an external reference for this project.
It have been given the label `myst-guide`, so it can be reference with `[](xref:myst-guide)`.

:::{literalinclude} ../../myst.yml
:start-at: references
:end-at: myst-guide
:lineno-match:
:::

:::{exercise} Reference the MyST guide
Create a reference to an object in the MyST guide.
Try referencing some different types of node, like pages, sections, paragraphs, figures and so on.
:::

:::{exercise} Add a new external reference
1. Edit `myst.yml` and add _The Turing Way_ (https://book.the-turing-way.org) as an external reference in the `references` block.
2. Use the label you gave _The Turing Way_ to create a reference.
:::

## Wikipedia

:::{exercise} Reference a Wikipedia page
Use `[](wiki:)` to create a reference to your favourite Wikipedia article.
:::

## DOIs

::::{exercise} Reference a document by its DOI
Use `[](doi:)` to create a reference to a document.

:::{hint}
You can find many documents with DOIs on [Zenodo](https://zenodo.org/)
:::
::::

## GitHub

Links to GitHub have dynamic tooltips which can show issues, pull requests, and lines of code.

::::{exercise} Reference items in GitHub
Use `[](https://github.com)` to create a references to GitHub objects.

:::{hint}
If you are not sure which GitHub repository to use, try [`mystmd`](https://github.com/jupyter-book/mystmd).
:::
::::
