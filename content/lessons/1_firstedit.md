---
numbering:
  title:
    offset: 0
---
(fundamentals)=
# Jupyter Book Fundamentals

## Anatomy of a Jupyter Book

A Jupyter Book is a collection of files and folders that together make up the content and structure of your book.
Jupyter Book 2 (JB2) supports both [Markdown](https://en.wikipedia.org/wiki/Markdown) files and [Jupyter Notebooks](https://en.wikipedia.org/wiki/Project_Jupyter#Jupyter_Notebook) as content sources. 
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

## Markdown
Markdown is a simple markup language: plain text that is *formatted* with small pieces of 'code'. This allows you to create rich, interactive books that combine text, code, and visualizations. This text can then be quickly exported to various other formats such as PDF, Word, HTML, etc.

```{figure} ../figures/MyST.PNG
:width:80%

Documents made in MyST Markdown can be converted to many different formats. These can be saved as JSON, or rendered to a website (like this one!) or any number of formats including [PDF & LaTeX](https://mystmd.org/guide/creating-pdf-documents), [Word](https://mystmd.org/guide/creating-word-documents), [React](https://mystmd.org/guide/quickstart-myst-documents), or [JATS](https://mystmd.org/guide/creating-jats-xml). Picture taken from the MYST documentation [^MYST].
```

[^MYST]: https://mystmd.org/guide/


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

```{iframe} https://www.youtube.com/embed/bLhvq4a-03U?si=GQaFuZGn2-3E4b5Z
:align: center
:width: 100%

Choose your file, click on edit and make changes. Ready? Commit your changes to your repository and see the output.
```

Optionally, make other changes in the text editor and when you're done, commit your changes to the "remote repository" by clicking the green `Commit changes` button.

The book will now be rebuilt. Once that's done, you can view the result on the GitHub page.
:::
:::{tab-item} Locally
Navigate to the file `Content/Lessons/1_firstedit.md` and open the file.

Change the text after the `#`. This is the **title** of the file.

Optionally, make other changes in the text editor.
Check the results by running `myst start` in the CLI and opening the local server `http://localhost:3000/`.
When you're done, commit your changes to the "remote repository".

The book will now be rebuilt.
Once that's done, you can view the result on the GitHub page as well.

:::
::::
````

:::{note} Commit summary
:class: dropdown
If you are working with multiple people in GitHub, or on a large project yourself, it is wise to give the commit a recognizable title (commit message) and optionally add a summary (extended description) of exactly what was changed, see also [this more elaborative description](https://book.the-turing-way.org/collaboration/github-novice/github-novice-firststeps/#committing-or-saving-your-changes). 
This way, you can detect and undo any errors early. You can also explain why certain changes were made.
:::

## Adding a page

The [](xref:myst-guide/table-of-contents) defines the structure of your Jupyter Book.
Items in your `myst.yml`'s `toc` will be added to the book's table of contents.
Markdown, TeX and Jupyter Notebook files will be rendered as pages (in the case of a website) or chapters (in the case of a document).

To add a new page from a Markdown file,

1. Create a new markdown file
2. Add some content to the file
3. Include in the [ToC](#lesson1_code_toc)

```{exercise} Add a new page
:label: ex-add-a-page
::::{tab-set}
:::{tab-item} Using the GitHub IDE
1. Create a new markdown file
  - navigate to the folder where you want to include the sourcefile
  - click `add file` / `+ Create new file`
  - create a clear name for the file and use the .md extension (e.g. `newfile.md`)
2. Create a [H1 heading](#headings_cheat_sheet)
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
2. Create a [H1 heading](#headings_cheat_sheet)
  - use for the header `#` and include the title
  - save your file
3. Include the file in the [ToC](#lesson1_code_toc).
  - navigate to the `myst.yml` file in the root folder
  - at the right location in your book, include the path to your file (e.g. `- file: content/lessons/newfile.md`)
  - save your changes and check the out on your local server.
:::
::::
```

## Using Headings

Similarly to how your table of contents gives structure to your Jupyter Book,
within a page you can build structure using headings.
You can use levels of headings from 1 to 6 to structure a page.

:::{note}
In the [book theme](xref:myst-guide/website-templates#default-web-themes), headings are shown, and can be used to navigate a page, in the Contents menu at the right of a page.
:::

:::{exercise} Add headings to your new page

Navigate to the Markdown file you added to the book in [](#ex-add-a-page).
You have already added a level one heading, the title of the page.

Add headings to represent the following structure.
Refer to the [cheat sheet](#headings_cheat_sheet) if you need a reminder on the syntax.

- Animals
  - Dogs
    - Bearded Collie
    - Irish Wolfhound
  - Cats
    - Calico
    - Tabby
  - Hippos
    - Common
    - Pygmy
- Food
  - Soup
    - Carrot and coriander
    - Miso
    - Gazpacho
  - Salad
    - Caesar
    - Greek
    - Niçoise
:::

## Essential typography

You should now be confident making changes locally or through the GH IDE.
Try making the changes indicated in the following exercise using the solution directive below.
Refer to the [cheat sheet](#cheat-sheet) if you need a reminder on the syntax.

:::{exercise} Typography
:label: ex_typography
Make this line bold.

Make this line italic.

Put these items in an unordered list,

Elm
Sycamore
Oak
Beech

Put these items in an ordered list,

Hydrogen
Helium
Lithium
Beryllium
Boron
Carbon

Put a line break between this sentence. And this sentence.

Make the following line an equation with a label,

F = m a

And reference that equation here.
:::

:::{solution} ex_typography
:class: dropdown
Optionally you can put your answers here.
:::

:::{hint}
Remember, new lines in a Markdown file don't create new paragraphs in the output.
See the [cheat sheet](#line-breaks) for a reminder.
:::

## Next steps

```{exercise} Going further
Try making some more changes to the page you created in [](#ex-add-a-page).
Find an element in the [cheat sheet](#cheat-sheet) or [MyST Markdown guide](xref:myst-guide) that you haven't used yet, for example abbrevitions or a code block, and try adding it.
Remember to check the result regularly.
```
