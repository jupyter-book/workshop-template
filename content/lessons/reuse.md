---
numbering:
  title:
    offset: 0
---

# Reusing and sharing content

MyST has strong support for referencing and reusing content.
MyST nodes can be referenced or embedded, even from external projects!
These features help to more seamlessly share content between MyST projects, so your project can become part of a larger network of resources.

## Referencing

### Internally

Review the [references section of the cheat sheet](#cheatsheet-ref) for a reminder of the syntax.

:::{exercise} Global labels
The labels you give MyST nodes are "global".
You can refer to them in any part of your project, not just on the page where you defined them.

Reference the equation with label `eq_newton` from the cheat sheet [here](x).
:::

:::{exercise} Label anything
Add a label to this paragraph.

And reference it [here](x).
:::


### External MyST projects

The [MyST guide](xref:myst-guide) has already been added as an external reference for this project.
It has been given the label `myst-guide`, so it can be referenced with `[](xref:myst-guide)`.

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

## Embedding

The [`embed` directive](xref:myst-guide/embed#docs-embed) allows you to reuse content in-place.
This is helpful if you want to have the same content in two places, without repeating the source or interrupting the flow of a page with a link.

### Internally

::::{exercise}

Embed the table `tl_basic_formatting` from the cheat sheet using the `embed` directive syntax

```markdown
:::{embed} label
:::
```
::::

### External MyST projects

Just like with cross-references, you can also embed content from external MyST projects.

::::{exercise}
Embed the figure `sunset-figure` from the [MyST guide](xref:myst-guide)

:::{hint}
Remember that to reference an external MyST project you use `xref:` and the label given to the project in `myst.yml`.
In this case that is `xref:myst-guide`.
:::
::::

## Referencing other internet resources

Like with MyST references, some links to non-MyST resources are handled specially and have dynamic, interactive tooltips.

### Wikipedia

:::{exercise} Reference a Wikipedia page
Use `[](wiki:)` to create a reference to your favourite Wikipedia article.
:::

### DOIs

::::{exercise} Reference a document by its DOI
Use `[](doi:)` to create a reference to a document.

:::{hint}
You can find many documents with DOIs on [Zenodo](https://zenodo.org/)
:::
::::

### GitHub

Links to GitHub have dynamic tooltips which can show issues, pull requests, and lines of code.

::::{exercise} Reference items in GitHub
Use `[](https://github.com)` to create a references to GitHub objects.

:::{hint}
If you are not sure which GitHub repository to use, try [`mystmd`](https://github.com/jupyter-book/mystmd).
:::
::::
