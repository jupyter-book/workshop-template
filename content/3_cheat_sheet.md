# Markdown (Cheat sheet)

Below is a set of frequently used markdown commands for Jupyter Book 2 made with MyST. A good practice is to download the source file by clicking the download icon at the top right of this page and inspect the code. 


## Book structure
We can distinguish between two structures: that of the book's content (a collection of different documents), and the (internal) structure of the chapters which consists of content structured in sections and subsections.

### Table of Contents
In the `myst.yml` file, you can specify the structure of the book as shown in {numref}`fig_toc`. Here you can indicate which files belong to the book and in what order. You can also create dropdown menus. When not specifying a ToC, all files are automatically included in alphabetical order.

```{figure} figures/toc.png
:width: 70%
:align: center
:name: fig_toc

The Table of Contents (ToC) for this book.
```

If you create a new file, you need to add it to the `myst.yml` file to include it in the book.

### Chapters, sections and subsections    
To distinguish between chapter, section, and subsection (and further), use a number of `#` symbols, as shown below.

```markdown
# H1 chapter  
## H1.1 section   
### H1.1.3 subsection  
```

```{tip}
Do not number your chapters and sections! This happens automatically.
```

```{note}
Files below `children` in the `myst.yml` file are considered sections, even when the heading has a single `#`. 
```

## Basic Formatting
Markdown is a markup language where text formatting is done with small pieces of code (just like HTML). This is a table with some frequently used formatting options.

| Element | Syntax | Example | 
| --- | --- | --- |
| Bold | `**bold text**` | **Bold** |
| Italic | `*italics*` | *Italics* |
| Emphasis | `***emphasis***` | ***emphasis*** |
| Inline Formula | `$F = m \cdot a$` | $F = m \cdot a$ |
| Footnote | ` - A footnote reference[^myref]` <br> `[^myref]: This is an auto-numbered footnote definition.` | - A footnote reference[^myref] | 
 
[^myref]: This is an auto-numbered footnote definition.


You can create a new line by either a hard enter and a blank line, a `\` at the end of the line and enter, or two spaces at the end of the line.

### New Line

Generally, in markdown, a single hard enter does not create a new line. You need to use one of the options below.

::::{tab-set}
:::{tab-item} ways for a new line
A new line with double space.  
A new line with a `\`.\
A new line with a hard enter and blank line.

No new line with just a hard enter and text on the next line.
Like this
:::
:::{tab-item} syntax
```markdown
A new line with double space.  
A new line with a `\`.\
A new line with a hard enter and blank line.

No new line with just a hard enter and text on the next line.
Like this
```
:::
::::

### Equations & Symbols

For STEM subjects, mathematical equations and symbols ($\Delta \lambda$) are essential. You can include equations in JB's. What is possible in LaTeX is also possible in JB, for example:

$$ F_{res} = m \cdot a$$ (eq:Newton)

Where labeled equations, such as {eq}`eq:Newton`, can be referenced.

`$$ Equation $$ (<label>)`

But you can also include inline equations like this: $s=v_{avg}t$. Use a single dollar sign before and after: `$ Equation $`

|Name|Script|Symbols|
|---|---|---|
|root|`\sqrt{4}`|$\sqrt{4}$|
|power|`^{2x}`|$^{2x}$|
|fraction|`\frac{2}{3}`|$\frac{2}{3}$|
|subscript|`_{avg}`|$_{avg}$|
|superscript|`^{N}`|$^{N}$|
|multiply|`\cdot`|$\cdot$|

Some examples:
|Name|Script|Output|
|---|---|---|
|Derivative|`\frac{\Delta f}{\Delta t}`|$\frac{\Delta f}{\Delta t}$|
|Integral|`\int_a^b dx`|$\int_a^b dx$|
|sine|`sin(x)`|$sin(x)$|

More: https://en.wikibooks.org/wiki/LaTeX/Mathematics


## Lists & tables


### Lists Option 1
::::{tab-set}
:::{tab-item} list
1. item 1
1. item 2.
1. item 3.
:::
:::{tab-item} syntax
```markdown
1. item 1
1. item 2.
1. item 3.
```
:::
::::

### Lists Option 2
::::{tab-set}
:::{tab-item} list
1. item 1
2. item 2.
3. item 3.
:::
:::{tab-item} syntax
```markdown
1. item 1
2. item 2.
3. item 3.
```
:::
::::


### Tables

Tables are created with the separator `|`

::::{tab-set}
:::{tab-item} Tables

```
|Header 1|Header 2|Header 3|
|---|---|---|
|text 1|text 2|text 3|
|text 4|text 5|text 6|
```

:::

:::{tab-item} MyST Syntax

````markdown
```
|Header 1|Header 2|Header 3|
|---|---|---|
|text 1|text 2|text 3|
|text 4|text 5|text 6|
```
````

:::
::::

Or via ...

::::{tab-set}
:::{tab-item} Tables

```{list-table} Overview of sanctions for certain behavior
:header-rows: 1
:name: tl_sanctions
* - Behavior
    - Sanction for 1st time
    - Sanction for 2nd time
* - Not (timely or with a valid reason) deregistered 
    - A penalty                                       
    - exclusion              
```

:::

:::{tab-item} MyST Syntax

````markdown
```{list-table} Overview of sanctions for certain behavior
:header-rows: 1
:name: tl_sanctions
* - Behavior
    - Sanction for 1st time
    - Sanction for 2nd time
* - Not (timely or with a valid reason) deregistered 
    - A penalty                                       
    - exclusion              
``` 
````

:::
::::

Method 2 has the advantage of allowing references to {numref}`Table {number} <tl_sanctions>`

### Tabs

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
Will create this tab:

::::{tab-set}
:::{tab-item} Tab 1
Text in tab 1
:::

:::{tab-item} Tab 2
Text in tab 2
:::
::::

### Checklists 
::::{tab-set}
:::{tab-item} list
- [x] Create a markdown cheat sheet
- [x] Publish online
- [ ] Let others test
:::
:::{tab-item} syntax
```markdown
- [x] Create a markdown cheat sheet
- [x] Publish online
- [ ] Let others test
```
:::
::::


## Admonitions
You can add special blocks that are highlighted in the text. See, for example, the warning below.

```{warning}
Here is a warning
```

Created using: 

````markdown
```{warning}    
Here is a warning
```
````

There are different variants such as:
* tip 
* admonition 
* warning 
* note 
* objective 
* see also ...

```{tip} The golden...
Exercises are a special kind of admonition.
```

### Exercises
A special case is the exercises which can be labeled and can come with a solution that is linked to the exercise: 
```{exercise} Exercise 1
:label: ex_opdr_1

Calculate $4+2$
```

```{solution} ex_opdr_1
:class: dropdown

6
```

## Figures
A site/book naturally needs figures. There are roughly two ways to add a figure:

*Quick figure, without formatting options*

| Quick figure | `![](link to figure)` |

*Better way with more control:*

::::{tab-set}
:::{tab-item} Figures

```{figure} https://github.com/rowanc1/pics/blob/main/sunset.png
:label: fig_sunset
:width: 70%
:align: center

With a nice caption
```

:::

:::{tab-item} MyST Syntax

````markdown
```{figure} https://github.com/rowanc1/pics/blob/main/sunset.png
:label: fig1
:width: 70%
:align: center

With a nice caption
```
````

:::
::::

Here we used figures hosted online, but you can also add figures to a folder (e.g., called *Figures*), and then use a relative path.


## YouTube
To embed YouTube videos on the site, you need the embed YT link. The code is then:

::::{tab-set}
:::{tab-item} YouTube
```{iframe} https://www.youtube.com/embed/YDBr1Lof_mI?si=thWYK9MFi5QJv-tW
:width: 80%
:align: center

A super fun video from the project [Show the Physics](https://interactivetextbooks.tudelft.nl/showthephysics)
```
:::
:::{tab-item} syntax
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
Embedded YT videos are not included in the PDF. A solution could be to include a QR code, for example.
```

(sec-ref)=
## References & Links

You can included [links](https://interactivetextbooks.tudelft.nl/showthephysics) like this. With the markdown syntax: `[text](link)`.

It also possible to include reference through the reference.bib file, or directly by including the DOI: [](https://doi.org/10.1088/1361-6552/abf208) (syntax: `[](https://doi.org/10.1088/1361-6552/abf208)`) or [@doi:10.1088/1361-6552/abf208] (syntax: `[@doi:10.1088/1361-6552/abf208]`).

Below a few examples of links and references to labeled items.

::::{tab-set}
:::{tab-item} list
* This is a [hyperlink](https://nos.nl)  
* This is a reference to equation {eq}`eq:Newton`  
* This is a reference to a table like {numref}`Table {number} <tl_sanctions>`  
* This is a reference to a figure like {numref}`Figure {number} <fig_sunset>`  
:::
:::{tab-item} syntax
```markdown
* This is a [hyperlink](https://nos.nl)  
* This is a reference to equation {eq}`eq:Newton`  
* This is a reference to a table like {numref}`Table {number} <tl_sanctions>`  
* This is a reference to a figure like {numref}`Figure {number} <fig_sunset>`  
```
:::
::::
