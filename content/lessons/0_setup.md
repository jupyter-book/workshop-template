---
numbering:
  title:
    offset: 0
---

# Set up a new repository

Follow these instruction to use the GitHub template repository to create your own book for this workshop:

1. Go to this [repository](https://github.com/FreekPols/JB2_book_template.git)
2. Click the green button `use this template` and click `create a new repository`.
3. Choose a proper name of your repository (this will be also part of your URL!) and choose the option `public`.
4. In your repository, click on `settings` and in the left menu on Pages and choose `Github Actions`

```{tip}
GitHub Actions will be covered later in this workshop, so if you have no idea what this is, don't worry!
```

```{iframe} https://www.youtube.com/embed/UZpo_S8QNZI?si=dz-xbWzOyUUlIwJ5
:name: vid_1

Follow these steps to create your own repository from the template.
```

5. Click on `code` and click on the `gear-icon` (near **About**) at the right site of the page. 
6. Check the box **Use your GitHub Pages website**.
7. Go to `Actions` in the topmenu, click on the (red) `initial commit` and click `re-run all jobs`

The book will now be deployed again - where now it can actually load GitHub pages. 

``` {iframe} https://www.youtube.com/embed/gQP_gjrh7rQ?si=DWiL_J27_a35RV__
:name: vid_2

Follow these steps to create your own GHpages from the template.
```

8. Use the book link  (`code` $\rightarrow$ below **About**) to your Github page where the book is hosted.
9. The output resembles {numref}`Figure {number} <fig_startscreen>`.

```{figure} figures/startscreen.png
:name: fig_startscreen
:width: 100%

Once the book has been deploy, you can visit your site which looks like this.
```

```{note} Attribution
:icon: false
This template workflow has been adapted from [teachbooks](https://teachbooks.io)
```

## Repo folder structure

Your GitHub repository looks like the one shown in {numref}`fig_folderstructure`. We have the following subfolders:

- Content: the source files of your book (in markdown or jupyter notebook format)
- Exports: the folder which may include a pdf export of your book
- Figures: the folder which includes figures for your book (*could be in content folder*)
- Lessons: the folder which includes the lessons of this tutorial (*could be in Content folder*)
- .github/workflows: the folder which includes the GitHub Actions (automated workflows) to build and deploy your book
- css: the folder which includes the custom css file to change the layout of your book
- pdf_template_book: the folder which includes the [typst template](https://github.com/myst-templates/plain_typst_book) to create a pdf export of your book

```{figure} figures/Folderstructure.png
:name: fig_folderstructure
:width: 100%

Once the book has been deploy, you can visit your site which looks like this.
```

## Make and deploy changes

You have a number of options for making changes to the book's source and seeing how they affect the output.

::::{tab-set}
:::{tab-item} Using the GitHub IDE

It is possible to work directly in the GitHub environment: no need to install anything as this is already covered with the GH Actions that we created.

1. Click on the index.md file in the Content folder
2. Click on the drop down icon next to the pencil icon and choose `open in github.dev` This will start the GitHub development environment where you can edit the files directly in your browser.
3. Edit the file by replacing the names with your own and commit your changes, see [](#vid_3)

```{iframe} https://www.youtube.com/embed/MIJUMsTEfzY?si=upISYp21twTtAIFs
:name: vid_3

Working directly in the GitHub development environment.
```

Now, if you go back to your repository and click on `Actions` you will see that the workflow is running to build and deploy your book. After a few minutes, you can refresh your book page and see your changes live!
:::
:::{tab-item} Using your favourite editor
You can also make changes locally then push them back to your GitHub repository.
1. Clone the repository to your local machine using Git.

```console
git clone git@github.com:<github_user_name>/JB2_book_template.git
```

2. Make changes to the content files in the `content` directory using your text editor.
3. Commit and push your changes. For example

```console
git commit -a
git push -u origin main
```

Now, if you go back to your repository and click on `Actions` you will see that the workflow is running to build and deploy your book. After a few minutes, you can refresh your book page and see your changes live!

:::
:::{tab-item} Entirely locally 🌶 
If you prefer, you can also work entirely locally using command-line tools and a text editor.

1. Clone the repository to your local machine using Git.

```console
git clone git@github.com:<github_user_name>/JB2_book_template.git
```

2. Install MyST Markdown. Using `npm` or `pip`

```console
npm install -g mystmd
```

```console
pip install mystmd
```

`````{hint}
To build a pdf using Typst you will need to install the Typst CLI.
There are a [number of options for installing Typst](https://github.com/typst/typst?tab=readme-ov-file#installation).

````{dropdown} Common options for installing Typst
Using brew

```console
brew install typst
```

Using cargo

```console
cargo install --locked typst-cli
```

Using winget

```console
winget install --id Typst.Typst
```

````
`````

3. Make changes to the content files in the `content` directory using your text editor.
4. Serve the book locally.

```console
myst start
```

5. Preview the book in your browser at [`http://localhost:3000`](http://localhost:3000)

```{tip}
Once the MyST server is running, it will automatically update as you make changes to the source.
```

:::
::::

## Create a pdf export
A clear advantage of JB2 over JB1 is the ability to easily create a high quality pdf export of your book (as well as other formats). We included a GitHb Action workflow that automatically creates a pdf export of your book using Typst when you push changes to your repository. You can also create the pdf locally if you have the Typst CLI installed. We cover the pdf export [later in more detail ](#pdfoutput)

```{tip}
Checkout the content on your mobile phone as well! It just looks amazing.
```
