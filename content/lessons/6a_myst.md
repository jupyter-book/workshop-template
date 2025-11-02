---
numbering:
  title:
    offset: 1
---

# MyST Document Creation 🌶

This page introduces a few key concepts that will help understand how Jupyter Book 2 creates documents from source files written using MyST Markdown. We are particularly interested in understanding how _themes_ and _templates_ are used to create a website and PDF, respectively. 

Only a very brief overview is provided here; for additional technical explanation, refer to the [stack overview section of the MyST Guide](https://mystmd.org/guide/overview), as well as the [SciPy Paper](https://proceedings.scipy.org/articles/hwcj9957).

```{tip}
The term "MyST" is used here, rather than "Jupyter Book", because MyST is the underlying technology that Jupyter Book 2 uses to create documents. [As described elsewhere](https://proceedings.scipy.org/articles/hwcj9957#jupyter-book-2-a-distribution-of-myst-components):

> Jupyter Book 2 is a lightweight distribution and configuration layer on top of these and other components of the MyST ecosystem. It is meant to provide an opinionated experience of MyST–for example, by turning on certain features by default...

```

## Key MyST Components

As you already know, Jupyter Book 2 is able to convert MyST Markdown written `*.md` and `*.ipynb` source files into websites: online books. However, there are many other formats that MyST can convert to, including PDF, LaTeX, Word, JATS XML, and more. The process is illustrated in the following figure:


```{figure} ../figures/MyST.PNG
:width:80%

Documents made in MyST Markdown can be converted to many different formats. These can be saved as JSON, or rendered to a website (like this one!) or any number of formats including [PDF & LaTeX](https://mystmd.org/guide/creating-pdf-documents), [Word](https://mystmd.org/guide/creating-word-documents), [React](https://mystmd.org/guide/quickstart-myst-documents), or [JATS](https://mystmd.org/guide/creating-jats-xml). Picture taken from the MYST documentation [^MYST].
```

[^MYST]: https://mystmd.org/guide/

In the demonstration below below, each tab illustrates the various output formats for a given MyST Markdown input:

:::{myst}
# This is a heading
This is a paragraph with **bold** and *italic* text.
- This is a list item
- Another list item
```{warning} raw HTML
You can also include raw HTML in your Markdown files, but this will not be rendered in the PDF output.
```
:::

## MyST Build Process

The "build" process, the process of converting MyST Markdown into a given output format, is more complex than the figure above suggests. In fact, it has [5 key steps](https://mystmd.org/guide/overview#overview-build-process): writing, parsing, resolving, rendering and exporting. Of this process, illustrated below, only the final step is of interest to us here, as it is where the rendered components of a document are combined with a _theme_ (for websites) or a _template_ (for PDF's) to create the final output document.

```{figure} ./figures/myst-build.JPEG
:width:100%

High-level overview of Jupyter Book 2 components. Picture taken from Figure 1 of the Scipy paper [^scipy-paper].
```
[^scipy-paper]: https://proceedings.scipy.org/articles/hwcj9957#overview-of-jupyter-book-2s-architecture

## Themes and Templates

For our purposes, a _theme_ or _template_ defines the final appearance of our document. Though a concise explanation is provided [here](https://mystmd.org/guide/overview#overview-themes), for this workshop it is sufficient to know that there are a number of different themes and templates available in the MyST ecosystem, and that it is possible to customize them to a high degree. An overview is provided at the [`myst-templates` GitHub organization](https://github.com/myst-templates).

Note in particular that there are currently only two themes in this organization: `book-theme` and `article-theme`. These are the [two themes bundled with MyST](https://mystmd.org/guide/website-templates#default-web-themes) and correspond to the two types of _websites_ that can be created. The code snippet below is from the `myst.yml` file of this book, which indicates the `book-theme` is used:

:::{literalinclude} ../../myst.yml
:start-at: site:
:end-at: hide_authors: true
:lineno-match:
:caption: Example of the `book-theme` specified in the `myst.yml` file.
:label: include_book_theme
:::

There is a relatively large number of templates listed in the [`myst-templates` GitHub organization](https://github.com/myst-templates), the vast majority of which create LaTeX documents (i.e., `*.tex` files). In fact, many of these templates are for articles formatted for publishing with specific journals and are used in combination with websites created using the `article-theme` to generate a PDF. The code snippet below is from the `myst.yml` file of this book, which indicates the `book-theme` is used:

:::{literalinclude} ../../myst.yml
:start-at: exports:
:end-at: id: output-pdf
:lineno-match:
:caption: Example of the `book-theme` specified in the `myst.yml` file.
:label: include_lapreprint
:::

## Summary

That's enough detail about the MyST ecosystem for now. The main takeaways from this page are to recognize:
- themes and templates are used to customize the creation of final documents for a given source
- this book is initially set up with the `book-theme` for website generation and the `lapreprint-typst` template for PDF generation

Up to this point in the workshop you have been modifying the source code and using the `book-theme` to view changes on the rendered website; however, you have not yet generated a PDF. After a quick introduction to LaTeX and Typst on the following page, we will do just that in the next round of exercises! 