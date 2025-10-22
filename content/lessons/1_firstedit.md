---
numbering:
  title:
    offset: 0
---
# Jupyter Book Fundamentals

## Anatomy of a Jupyter Book

A Jupyter Book is a collection of files and folders that together make up the content and structure of your book.
The structure of the book is specified in the `myst.yml` file, which is located in the root directory of your book.
This file contains information about the title, author, and other metadata of the book, as well as documents and its structure to build the book itself.

:::{literalinclude} ../../myst.yml
:start-at: # See docs
:end-at: content
:lineno-match:
:caption: The head of this book's `myst.yml`
:label: less1_code_head
:::


```{tip} Official documentation
See [here](https://mystmd.org/guide/table-of-contents) for a full explanation of the structure and TOC and [here](https://mystmd.org/guide/quickstart#configure-site-and-page-options) for more the website options.
```

## Your first change

As explained in the previous chapter, your files are on GitHub and the template ensures the book is built.
You can make changes directly to the files online in GitHub, and create or upload new files.

Some files are already present in the template book.
The folder structure is shown below

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
Navigate to the file `Content/Lessons/1_firstedit.md`. Then click on the pencil on the right (edit this file).

Change the text after the `#`. This is the **title** of the file.


```{figure} figures/firstedit.*
:width: 100%

Choose your file, click on edit and make changes. Ready? Commit your changes to your repository and see the output.
```

Optionally, make other changes in the text editor and when you're done, commit your changes to the "remote repository" by clicking the green `Commit changes` button.

The book will now be rebuilt. Once that's done, you can view the result on the GitHub page.
:::
:::{tab-item} Local
Navigate to the file `Content/Lessons/1_firstedit.md` and open the file.

Change the text after the `#`. This is the **title** of the file.

Optionally, make other changes in the text editor. Check the results by running `myst start` in the CLI and opening the local server `http://localhost:3000/`. When you're done, commit your changes to the "remote repository".

The book will now be rebuilt. Once that's done, you can view the result on the GitHub page as well.

:::
:::
::::
````

```{admonition} Commit summary
:class: dropdown
If you are working with multiple people in GitHub, or on a large project yourself, it is wise to give the commit a recognizable title (commit message) and optionally add a summary (extended description) of exactly what was changed, see also [this more elaborative description](https://book.the-turing-way.org/collaboration/github-novice/github-novice-firststeps/#committing-or-saving-your-changes). This way, you can detect and undo any errors early. You can also explain why certain changes were made.
```


## Create a new chapter
In order to make a new chapter, three things need to be done. 
1. A new markdown file should be created
2. A title should be specified in the file.
3. The file should be included in the [ToC](#lesson1_code_toc)

::::{tab-set}
:::{tab-item} Using the GitHub IDE
1. Create a new markdown file 
  - navigate to the folder where you want to include the sourcefile
  - click `add file` / `+ Create new file`
  - create a clear name for the file and use the .md extension (e.g. `newfile.md`)
2. Create a [H1 heading](#headings)
  - use for the header `#` and include the title
  - commit your changes
3. Include the file in the [ToC](#lesson1_code_toc).
  - navigate to the `myst.yml` file in the root
  - at the right location in your book, include the path to your file (e.g. `- file: content/lessons/newfile.md`)
  - commit your changes and check the output on GitHub pages.
:::
:::{tab-item} Locally
1. Create a new markdown file
  - navigate to the folder where you want to include the sourcefile
  - create a new file
  - create a clear name for the file and use the .md extension (e.g. `newfile.md`)
2. Create a [H1 heading](#headings)
  - use for the header `#` and include the title
  - save your file
3. Include the file in the [ToC](#lesson1_code_toc).
  - navigate to the `myst.yml` file in the root folder
  - at the right location in your book, include the path to your file (e.g. `- file: content/lessons/newfile.md`)
  - save your changes and check the out on your local server.
:::
::::

### Create a section with your favorite equation
Navigate back to your recently made markdown file and include a section including your favorite equation, consider you want an inline equation ($F = m a$) or centered and labeled:

$$ F = m a $$ (eq:NewtonFirst)


```{tip} 
Take a look at the [Cheatsheet page](#cheatsheet) to see how to add a formula and give it a try...

Don't forget to commit your changes!
```

```{exercise} Other changes
Try making some other changes, for example by further developing the structure of the page into sections and subsections, each with some **text**. *Check* the result regularly.
```
