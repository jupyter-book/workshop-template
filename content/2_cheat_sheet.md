(cheat-sheet)=
# Markdown Cheat Sheet

Below is a set of frequently used markdown commands for Jupyter Book 2 made with MyST. A good practice is to download the source file by clicking the download icon at the top right of this page and inspect the code.

## Book structure

We can distinguish between two structures: that of the book's content (a collection of different documents), and the (internal) structure of the chapters which consists of content structured in sections and subsections.

### Table of Contents

In the `myst.yml` file, you can specify the structure of the book as shown in [](#code_toc).
Here you can indicate which files belong to the book and in what order.
You can also create dropdown menus in your ToC by including `children`.
When not specifying a ToC, all files are automatically included in alphabetical order.

:::{literalinclude} ../myst.yml
:start-after: toc
:end-at: - file: content/gallery.md
:lineno-match:
:caption: The Table of Contents (ToC) for this book.
:label: code_toc
:::

If you have specified a ToC and create a new file, you'll need to add it to the `myst.yml` file to include it in the book.
Note that this is a {abbr}`.yml (a human-readable data format used to store and exchange structured data.)` file rather than a .md file.


(headings_cheat_sheet)=
### Headings

To make sections within a page, use a number of `#` symbols at the beginning of a line.
The more `#`s increases the level of the heading.

```markdown
# Heading level 1
## Heading level 2
### Heading level 3
```

Typically, a page only has a single level 1 heading, the page's title and higher level headings are used for sections and subsections.

```{tip}
Do not number your chapters and sections! This happens automatically.

Note also that a structured sections are preferred, that is not skipping a heading.

A chapter outline based on the headings in the page and their hierarchy is created automatically and shown in the right sidebar.
```


## Basic Formatting

Markdown is a markup language where text formatting is done with small pieces of code (just like HTML). This is a table with some frequently used formatting options.

:::{table} Some basic Markdown text formatting
:label: tl_basic_formatting
:align: center
| Element | Syntax | Example |
| --- | --- | --- |
| Bold | `**bold text**` | **Bold** |
| Italic | `*italics*` | *Italics* |
| Emphasis | `***emphasis***` | ***emphasis*** |
| Inline Formula | `$F = m \cdot a$` | $F = m \cdot a$ |
| Footnote | ` - A footnote reference[^myref]` <br> `[^myref]: This is an auto-numbered footnote definition.` | - A footnote reference[^myref] |
:::

[^myref]: This is an auto-numbered footnote definition.


You can create a new line by either a hard enter and a blank line, a `\` at the end of the line and enter, or two spaces at the end of the line.

(line-breaks)=
### New Lines

Generally, in markdown, a single hard enter does not create a new line. You need to use one of the options below.

::::{card}
A new line with double space.
A new line with a `\`.\
A new line with a hard enter and blank line.

No new line with just a hard enter and text on the next line.
Like this
:::{dropdown} Markdown syntax
```markdown
A new line with double space.
A new line with a `\`.\
A new line with a hard enter and blank line.

No new line with just a hard enter and text on the next line.
Like this
```
:::
::::

## Mathematics and equations

For STEM subjects, mathematical equations and symbol are essential.
You can include equations in JupyterBooks using the LaTeX syntax for mathematics.

Labelled equations using double dollars, such as [](#eq_newton), can be referenced.

::::{card}
$$ F_{\mathrm{res}} = m \cdot a$$ (eq_newton)
:::{dropdown} Markdown syntax
```markdown
$$ F_{\mathrm{res}} = m \cdot a$$ (eq_newton)
```
:::
::::


But you can also write inline equations with single dollars.

::::{card}
$s=v_{\mathrm{avg}}t$
:::{dropdown} Markdown syntax
```markdown
$s=v_{\mathrm{avg}}t$
```
:::
::::

:::{table} Some examples of LaTeX mathematics notation
:label: tl_latex_maths
:align: center
| Name              | Syntax                      | Output                      |
| ---               | ---                         | ---                         |
| Greek script      | `\Delta \lambda`            | $\Delta \lambda$            |
| root              | `\sqrt{4}`                  | $\sqrt{4}$                  |
| superscript/power | `x^{2a}`                    | $x^{2a}$                    |
| fraction          | `\frac{2}{3}`               | $\frac{2}{3}$               |
| subscript         | `x_{\mathrm{avg}}`          | $x_{\mathrm{avg}}$          |
| multiply          | `a \cdot b`                 | $a \cdot b$                 |
| derivative        | `\frac{\Delta f}{\Delta t}` | $\frac{\Delta f}{\Delta t}$ |
| integral          | `\int_a^b f(x) \mathrm{d}x` | $\int_a^b f(x) \mathrm{d}x$ |
| sine              | `\sin(x)`                   | $\sin(x)$                   |
:::

You can read about more of the LaTeX mathematics syntax in [the LaTeX wikibook](https://en.wikibooks.org/wiki/LaTeX/Mathematics)

```{tip} Typst
Typst equations are also supported in Jupyter Book. See [Typst in Jupyter Book](https://mystmd.org/guide/math#typst-math) for more information.
```

## Lists

### Ordered lists

Ordered lists can be made with automatically numbered items.

::::{card}
1. item 1
1. item 2.
1. item 3.
:::{dropdown} Markdown syntax
```markdown
1. item 1
1. item 2.
1. item 3.
```
:::
::::

Or you can manually number the items

::::{card}
1. item 1
2. item 2.
3. item 3.
:::{dropdown} Markdown syntax
```markdown
1. item 1
2. item 2.
3. item 3.
```
:::
::::

### Unordered lists

Unordered lists use `-` or `*` for each item.

::::{card}
- a
- b
- c
:::{dropdown} Markdown syntax
```markdown
- a
- b
- c
```
:::
::::

### Checklists

You can also create checklists.
The checks are interactive, you can tick or untick them.

::::{card}
- [x] Create a markdown cheat sheet
- [x] Publish online
- [ ] Let others test
:::{dropdown} Markdown syntax
```markdown
- [x] Create a markdown cheat sheet
- [x] Publish online
- [ ] Let others test
```
:::
::::

```{note} Report issues
Jupyter Book 2 trusts on an active open source community. If you find any issues in your project, you can report them back to the [Jupyter Book GitHub repository](https://github.com/jupyter-book/mystmd/issues), like this issue on the checklist not rendering properly: [#2290](https://github.com/jupyter-book/mystmd/issues/2290). 

When reported, the developers will try to fix the issue as soon as possible - as can be seen above!
```

## Tables

In Markdown, tables are created with the separator `|`

::::{card}
|Header 1|Header 2|Header 3|
|---|---|---|
|text 1|text 2|text 3|
|text 4|text 5|text 6|
:::{dropdown} Markdown syntax
```markdown
|Header 1|Header 2|Header 3|
|---|---|---|
|text 1|text 2|text 3|
|text 4|text 5|text 6|
```
:::
::::

Using a `table` directive, like [](#tl_example) lets you add a caption and label so you can [reference](#cheatsheet-ref) it.

:::::{card}
::::{table} An example table
:name: tl_example
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| text 1   | text 2   | text 3   |
| text 4   | text 5   | text 6   |
::::
::::{dropdown} Markdown syntax
```markdown
:::{table} An example table
:name: tl_example
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| text 1   | text 2   | text 3   |
| text 4   | text 5   | text 6   |
:::
```
::::
:::::

## Blocks

### Tabs

::::::{card}
::::{tab-set}
:::{tab-item} Tab 1
Text in tab 1
:::

:::{tab-item} Tab 2
Text in tab 2
::::
:::::{dropdown} Markdown syntax
```markdown
::::{tab-set}
:::{tab-item} Tab 1
Text in tab 1
:::

:::{tab-item} Tab 2
Text in tab 2
:::
::::
```
:::::
::::::

### Cards

:::::{card}
```{card} Title
:header: header
:footer: footer

With some text
```
::::{dropdown} Markdown syntax
````markdown

```{card} Title
:header: header
:footer: footer

With some text
```

````
::::
:::::

### Grids
Cards can be arranged side by side, with the number of cards shown adapting to different screen sizes from small to large.
:::{grid} 1 1 2 2
```{card} With a nice header
And cool text
```
```{card} Also with a nice header
Without cool text
```
:::

::::{dropdown} Markdown syntax
````markdown

:::{grid} 1 1 2 2
```{card} With a nice header
And cool text
```
```{card} Also with a nice header
Without cool text
```
:::

````
::::



## Admonitions

You can add special blocks that are highlighted in the text. See, for example, the warning below.

::::{card}
```{warning} This is a warning without icon
:class: dropdown
:open: true
:icon: false
Here is a warning
```
:::{dropdown} Markdown syntax
````markdown
```{warning} This is a warning without icon
:class: dropdown
:open: true
:icon: false
Here is a warning
```
````
:::
::::

There are different variants such as:
* tip
* admonition
* warning
* note
* objective

Using [plugins](PLACEHOLDER) you can add your own custom admonitions:

```{experiment} Here is a custom admonition
Made for our [physics book](https://freekpols.github.io/Mechanica/) which includes experiments.
```

### Exercises

A special case is the exercises which can be labelled and can come with a solution that is linked to the exercise:

::::{card}
```{exercise} Exercise 1
:label: ex_opdr_1

Calculate $4+2$
```

```{solution} ex_opdr_1
:class: dropdown

6
```
:::{dropdown} Markdown syntax
````markdown
```{exercise} Exercise 1
:label: ex_opdr_1

Calculate $4+2$
```

```{solution} ex_opdr_1
:class: dropdown

6
```
````
:::
::::

(cheat_sheet_figures)=
## Figures
A site/book naturally needs figures. There are roughly two ways to add a figure:

Quick figure, without formatting options

```markdown
![](path/to/figure)
```

Better way with more control:

::::{card}
```{figure} https://github.com/rowanc1/pics/blob/main/sunset.png
:label: fig_sunset
:width: 70%
:align: center

With a nice caption
```
:::{dropdown} Markdown syntax
````markdown
```{figure} https://github.com/rowanc1/pics/blob/main/sunset.png
:label: fig_sunset
:width: 70%
:align: center

With a nice caption
```
````
:::
::::

Here we used figures hosted online, but you can also add figures to a folder (_e.g._, called `figures`), and then use a relative path (e.g. `../figures/sunset.png`).


## YouTube

To embed YouTube videos on the site, you need the embed YT link. The code is then:

::::{card}
```{iframe} https://www.youtube.com/embed/YDBr1Lof_mI?si=thWYK9MFi5QJv-tW
:width: 80%
:align: center

A super fun video from the project [Show the Physics](https://interactivetextbooks.tudelft.nl/showthephysics)
```
:::{dropdown} Markdown syntax
````markdown
```{iframe} https://www.youtube.com/embed/YDBr1Lof_mI?si=thWYK9MFi5QJv-tW
:width: 80%
:align: center

A super fun video from the project [Show the Physics](https://interactivetextbooks.tudelft.nl/showthephysics)
```
````
:::
::::

```{warning} YT in pdf
Embedded YT videos are not included in the PDF. A solution could be to include our [plugin](https://github.com/jupyter-book/myst-plugins) which creates a QR code that links to the video, as well as a thumbnail of the video - taken from YT.
```

Using the same iframe directive, you can also embed other web content, like quizzes from a repository:

```{iframe} https://tudelft.h5p.com/content/1292579840119552937/embed
:width: 100%

```

(cheatsheet-ref)=
## References & Links

You can include [links](https://interactivetextbooks.tudelft.nl/showthephysics) like this.
With the markdown syntax: `[text](link)`.
`link` can take a number of forms including,

- A URL
- A label prepended with a `#` (like in the examples of figures and equations here)
- A references to an external MyST project, using `xref:`
- A wikipedia page, using `wiki:`
- A DOI, using `doi:`

MyST lets you add labels to [any block of content](xref:myst-guide/cross-references#label-anything) by adding a label like `(label)=` before the block.
This is a great way to reference things like sections or paragraphs, which don't otherwise have a label like figure directives or equations.

If you leave the text empty, appropriate link text will be automatically generated.
When referencing objects with a name or number, you can use `{name}` and `{number}` (or `%s`) in `text` to use the name and number in the link text respectively.

Below are a few examples of references,

::::{card}
- This is a [hyperlink](https://nos.nl)
- This is a reference to equation [](#eq_newton)
- This is a reference to a table [](#tl_example) or [Tab. %s](#tl_example)
- This is a reference to a figure [](#fig_sunset) or [**Fig. {name}**](#fig_sunset)
- This is a reference to an external MyST project [](xref:myst-guide/external-references#myst-xref)
- This is a reference to a DOI [](https://doi.org/10.1088/1361-6552/abf208) or [](doi:10.1088/1361-6552/abf208)
- This is a reference to a Wikipedia page [](wiki:Project_Jupyter)
- This is a reference to a GitHub pull request [](https://github.com/jupyter-book/mystmd/pull/2106)
- This is a reference to a file in GitHub [](https://github.com/jupyter-book/mystmd/blob/d39d9d68b2d67002771d95a87b56334d2d853585/README.md?#L1-L5)
:::{dropdown} Markdown syntax
```markdown
- This is a [hyperlink](https://nos.nl)
- This is a reference to equation [](#eq_newton)
- This is a reference to a table [](#tl_example) or [Tab. %s](#tl_example)
- This is a reference to a figure [](#fig_sunset) or [**Fig. {name}**](#fig_sunset)
- This is a reference to an external MyST project [](xref:myst-guide/external-references#myst-xref)
- This is a reference to a DOI [](https://doi.org/10.1088/1361-6552/abf208) or [](doi:10.1088/1361-6552/abf208)
- This is a reference to a Wikipedia page [](wiki:Project_Jupyter)
- This is a reference to a GitHub pull request [](https://github.com/jupyter-book/mystmd/pull/2106)
- This is a reference to a file in GitHub [](https://github.com/jupyter-book/mystmd/blob/d39d9d68b2d67002771d95a87b56334d2d853585/README.md?#L1-L5)
```
:::
::::

:::{tip}
Note how many of the references have dynamic tooltips.
:::

## Citations

You can cite entries in a Bibtex bibliography using  `@`.
The bibliography file is named `reference.bib` and located at the project's root directory.

::::{card}
- @feynman1965feynman
- @feynman1965feynman [p. 750]
:::{dropdown} Markdown syntax
```markdown
- @feynman1965feynman
- @feynman1965feynman [p. 750]
```
:::
::::
