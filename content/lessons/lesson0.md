# Lesson 0: Head start with GH template 

This lesson gives you a head start in creating your own online book using GitHub and the template repository [JB2_book_template](https://github.com/FreekPols/JB2_book_template).


## Set up your own repository

Follow these instruction to use this template for your own book.

1. Go to this [repository](https://github.com/FreekPols/JB2_book_template.git)
2. Click the green button `use this template` and click `create a new repository`.
3. Choose a proper name of your repository (this will be also part of your URL!) and choose the option `public`.
4. In your repository, click on `settings` and in the left menu on Pages and choose `Github actions`

```{figure} ../figures/blank.png
<!-- ``` {figure} figures/start.mp4 -->
:name: vid_1

Follow these steps to create your own repository from the template.
```

5. Click on `code` and click on the `gear-icon` (near **About**) at the right site of the page. 
6. Check the box **Use your GitHub Pages website**.
7. Go to `actions` in the topmenu, click on the (red) `initial commit` and click `re-run all jobs`


The book will now be deployed again - where now it can actually load GitHub pages. 

```{figure} ../figures/blank.png
<!-- ``` {figure} figures/2ndpart.mp4 -->
:name: vid_2

Follow these steps to create your own GHpages from the template.
```



8. Use the book link  (`code` $\rightarrow$ below **About**) to your Github page where the book is hosted.
9. The output resembles {numref}`Figuur {number} <fig_startscreen>`.

```{figure} figures/startscreen.png
:name: fig_startscreen
:width: 100%

Once the book has been deploy, you can visit your site which looks like this.
```

## Repo folder structure

Your GitHub repository looks like the one shown in {numref}`fig_folderstructure`. We have the following subfolders:

- Content: the source files of your book (in markdown or jupyter notebook format)
- Exports: the folder which may include a pdf export of your book
- Figures: the folder which includes figures for your book (*could be in content folder*)
- Lessons: the folder which includes the lessons of this tutorial (*could be in Content folder*)
- .github/workflows: the folder which includes the GitHub actions (automated workflows) to build and deploy your book
- css: the folder which includes the custom css file to change the layout of your book
- pdf_template_book: the folder which includes the typst template to create a pdf export of your book

```{figure} figures/Folderstructure.png
:name: fig_folderstructure
:width: 100%

Once the book has been deploy, you can visit your site which looks like this.
```

::::{tab-set}
:::{tab-item} Using the GH IDE

It is possible to work directly in the GitHub environment: no need to install anything as this is already covered with the GH actions that we created. 

1. Click on the index.md file in the Content folder
2. Click on the drop down icon next to the pencil icon and choose `open in github.dev` This will start the GitHub development environment where you can edit the files directly in your browser.
3. Edit the file by replacing the names with your own and commit your changes (see  ... BROKEN REF
<!-- {numref}`vid_3`). -->

```{figure} ../figures/blank.png
<!-- ```{figure} figures/GHdev.mp4 -->
:name: vid_3

Working directly in the GitHub development environment.
```

Now, if you go back to your repository and click on `actions` you will see that the workflow is running to build and deploy your book. After a few minutes, you can refresh your book page and see your changes live!
:::
:::{tab-item} Working locally
**PLACEHOLDER: add instructions to work locally**
To work locally on your computer, follow these steps:

1. Clone the repository to your local machine using Git.
2. Install the necessary dependencies (e.g., Python, Jupyter) to build and preview the book.
3. Make changes to the content files in the `Content` folder.
4. Build the book locally using the provided scripts or commands.
5. Preview the book in your browser to see the changes.
:::