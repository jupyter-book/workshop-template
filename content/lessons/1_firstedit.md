---
numbering:
  title:
    offset: 0
---
# Make your own content

## Anatomy of a Jupyter Book

A Jupyter Book is a collection of files and folders that together make up the content and structure of your book. The structure of the book is specified in the `myst.yml` file, which is located in the root directory of your book. This file contains information about the title, author, and other metadata of the book, as well as documents and its structure to build the book itself.

:::{literalinclude} ../../myst.yml
:start-at: # See docs
:end-at: content
:lineno-match:
:caption: The head of this book's `myst.yml`
:label: less1_code_head
:::


```{card} Official documentation
See [here](https://mystmd.org/guide/table-of-contents) for a full explanation of the structure and TOC and [here](https://mystmd.org/guide/quickstart#configure-site-and-page-options) for more the website options.
```

## Your first changes via GitHub

As explained in the previous chapter, your files are on GitHub and the template ensures the book is built. You can make changes directly to the files online in GitHub, and create or upload new files.

Some files are already present in the template book. The folder structure is shown below

:::{literalinclude} ../../myst.yml
:start-after: toc
:end-at: - file: content/software.md
:lineno-match:
:caption: The Table of Contents (ToC) for this book.
:label: lesson1_code_toc
:::

We will now make a small change to one of the files and then look at the result of that change.

````{exercise} Your first change
::::{tab-set}
:::{tab-item} GH IDE
Navigate to the file `book/some_content/overview.md`. Then click on the pencil on the right (edit this file).

Change the text after the `#`. This is the title of the file.

``` {figure} ../figures/blank.png
<!-- ``` {figure} figures/eersteedit.gif -->
```

Optionally, make other changes in the text editor and when you're done, commit your changes to the "remote repository" by clicking the green `Commit changes` button.

The book will now be rebuilt. Once that's done, you can view the result on the GitHub page.
:::
:::{tab-item} Local
Navigate to the file `book/some_content/overview.md` and open the file.

Change the text after the `#`. This is the title of the file.

Optionally, make other changes in the text editor. Check the results by running `myst start` in the CLI and opening the local server `http://localhost:3000/`. When you're done, commit your changes to the "remote repository".

The book will now be rebuilt. Once that's done, you can view the result on the GitHub page as well.

:::
:::
::::
````

```{admonition} Commit summary
:class: dropdown
If you are working with multiple people in GitHub, or on a large project yourself, it is wise to give the commit a recognizable title (commit message) and optionally add a summary (extended description) of exactly what was changed. This way, you can detect and undo any errors early. You can also explain why certain changes were made.
```


## Create a chapter


### Create a section

### Include an equation

# Your first changes via GitHub

As explained in the previous chapter, your files are on GitHub and the template ensures the book is built. You can make changes directly to the files online in GitHub, and create or upload new files.

Some files are already present in the template book. The folder structure is shown in ... BROKEN REF
<!-- {numref}`Figure {number} <fig_templatecontent>`. -->

``` {figure} ../figures/blank.png
<!-- ``` {figure} figures/templatecontent.PNG -->
---
width: 80%
name: fig_templatecontent
---
The folder structure in the template book.
```

We will now make a small change to one of the files and then look at the result of that change.

````{exercise} Your first change
Navigate to the file `book/some_content/overview.md`. Then click on the pencil on the right (edit this file).

Change the text after the `#`. This is the title of the file.

``` {figure} ../figures/blank.png
<!-- ``` {figure} figures/eersteedit.gif -->
```

Optionally, make other changes in the text editor and when you're done, commit your changes to the "remote repository" by clicking the green `Commit changes` button.

The book will now be rebuilt. Once that's done, you can view the result on the GitHub page.
````

```{admonition} Commit summary
:class: dropdown
If you are working with multiple people in GitHub, or on a large project yourself, it is wise to give the commit a recognizable title (commit message) and optionally add a summary (extended description) of exactly what was changed. This way, you can detect and undo any errors early. You can also explain why certain changes were made.
```


## Your favorite equation

```{exercise} Add an equation
Take a look at the [Cheatsheet page](#cheatsheet) to see how to add a formula and give it a try...
```

## Other changes

```{exercise} Other changes
Try making some other changes, for example by further developing the structure of the page into sections and subsections, each with some text. View the result.
```
