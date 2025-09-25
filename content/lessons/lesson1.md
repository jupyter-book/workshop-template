# Lesson 1: Make your own content

## Anatomy of a Jupyter Book

A Jupyter Book is a collection of files and folders that together make up the content and structure of your book. The structure of the book is specified in the `myst.yml` file, which is located in the root directory of your book. This file contains information about the title, author, and other metadata of the book, as well as documents and its structure to build the book itself.

````{card} myst.yml file
```yaml
# See docs at: https://mystmd.org/guide/frontmatter
version: 1
project:
  # title:
  # description:
  keywords: []
  authors: []
  # github:
  # bibliography: []
site:
  template: book-theme
  # title:
  # options:
  #   logo: my_logo.png
  nav: []
  actions:
    - title: Learn More
      url: https://mystmd.org/guide
  domains: []
```
````


```{card} Official documentation
See [here](https://mystmd.org/guide/table-of-contents) for a full explanation of the structure and TOC and [here](https://mystmd.org/guide/quickstart#configure-site-and-page-options) for more the website options.
```

## Your first changes via GitHub &#127798; 

As explained in the previous chapter, your files are on GitHub and the template ensures the book is built. You can make changes directly to the files online in GitHub, and create or upload new files.

Some files are already present in the template book. The folder structure is shown below

````{card} ToC
```yml
  toc:                                            # table of contents
    - file: index.md                              # the landing page
    - file: content/1_intro.md
    - file: content/2_jup_nb.ipynb
    - file: content/3_cheat_sheet.md
    - file: content/4_pdfoutput.md
    - file: content/lessons/your_turn.md          
      children:                                   # dropdown menu
        - file: content/lessons/lesson0.md        # first item in dropdown, note indentation
        - file: content/lessons/lesson1.md
        - file: content/lessons/lesson2.md
        - file: content/lessons/lesson3.ipynb
        - file: content/lessons/lesson4.md
    - file: content/software.md                   # not in dropdown menu
```
````

We will now make a small change to one of the files and then look at the result of that change.

````{exercise} Your first change
::::{tab-set}
:::{tab-item} GH IDE
Navigate to the file `book/some_content/overview.md`. Then click on the pencil on the right (edit this file).

Change the text after the `#`. This is the title of the file.

``` {figure} Figures/eersteedit.gif
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

<<<<<<< HEAD:content/lessons/Lesson1.md
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
=======
>>>>>>> origin/go-back-in-time:content/lessons/lesson1.md

## Adding a figure

A figure sometimes says more than 1000 words...

![External image](https://polslab.tnw.tudelft.nl/figures/training.JPG)

If we want to add a figure to our book, we can refer to another website (as in the figure above). However, this carries the risk that the figure will no longer be visible if it is moved from its location. It is therefore better to have the figure as a local source file.

So, we first need to upload a figure to GitHub and then refer to that figure in our file. (Note! This will become much easier later.)

`````{exercise}
On GitHub, under the `code` tab...

1. Navigate to book/figures and click on `add file` {fa}`right-long` `Upload files`.

```` {figure} ../figures/blank.png
<!-- ```` {figure} figures/incl_fig.PNG -->
---
width: 50%
---
add file in the folder
````
2. Choose the figure you want to add (remember the file name!).
3. Commit your changes to GitHub (the file will be uploaded).
4. Navigate to book and open `intro.md` and click `edit this file`.
5. Copy the code below into that file, and change the figure name to your own figure's name.

````{code} myst
``` {figure} figures/incl_fig.PNG
---
width: 50%
name: fig_myfirstfigure
---
add file in the folder
```
````

6. Commit your change and view the result on GitHub pages.

`````

```{warning}
The code is case sensitive. So it matters whether your extension is .png or .PNG
```

```{tip}
We have a page with all important [codes](./Cheatsheet.md).

You can find more information about figure options [here](https://teachbooks.io/manual/basic-features/figures.html).
```

You can position figures in different places (left / center / right / margin), adjust the size, add a caption, etc. Check the documentation above and try out the different settings.

## Your favorite equation

```{exercise} Add an equation
Take a look at the [Cheatsheet page](./Cheatsheet.md) to see how to add a formula and give it a try...
```

## Other changes

```{exercise} Other changes
Try making some other changes, for example by further developing the structure of the page into sections and subsections, each with some text. View the result.
```
