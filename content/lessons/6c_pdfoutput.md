---
numbering:
  title:
    offset: 1
---

# Create a PDF 🌶

With a general understanding of document creation using MyST and our choice to use Typst for PDF generation, you are ready to create a PDF from your book repository using Jupyter Book.

In this lesson, we will:
- Install Typst (or use it within a GitHub Action workflow if working online-only)
- Generate a PDF using the `lapreprint-typst` template
- Set up and use the `plain_typst_book` template
- Modify the GitHub Action workflow to generate a PDF
- Explore how the PDF can be customized and shared via the book website

```{warning}
To complete this lesson locally, you will need to install Typst. If this is not possible, or you are following the online-only path, you can complete the exercises using GitHub Actions. As before, the exercises in this lesson use **Locally** and **Online** to distinguish instructions for each case.

This lesson also uses GitHub Actions for _both_ local and online approaches. If you struggle with some of the GHA exercises below, refer to [the previous lesson](#gha-workflows).
```

## Install Typst

To produce a PDF output locally, you need to have Typst installed on your system. 

````{exercise} Install Typst

::::{tab-set} 
:::{tab-item} Locally

Install Typst using the nstructions available at the [Typst GitHub repo](https://github.com/typst/typst?tab=readme-ov-file#installation) and Jupyter Book 2 context is provided [here](xref:myst-guide/creating-pdf-documents#typst-install).

Check whether Typst is correctly installed by running the following command in your terminal:

```console
typst --version
```
:::
:::{tab-item} Online

Until you get to the Lesson "PDF output with GH Actions" you won't be generating PDF's, but you can still follow the exercise to learn how the template is defined and used in your Jupyter Book.

:::
::::
````

## Generate a PDF

Once Typst is installed and available in your terminal it can be used with Jupyter Book to generate a PDF file.


````{exercise} Generate a PDF of your book

::::{tab-set} 
:::{tab-item} Locally

Generate a PDF using the command `jupyter book build --pdf`.

View the PDF and observe how the contents of your website are formatted in the PDF document.

Next, review the contents of the `myst.yml` file and answer the following questions:
- What template is being used?
- Where is the PDF output file saved after being generated?
:::
:::{tab-item} Online

Review the contents of the `myst.yml` file and answer the following questions:
- What template is being used?
- Where is the PDF output file saved after being generated?
:::
::::
````

```{tip} Good practice with PDFs and Git
Git is not intended for use with binary files like PDF's. When working with PDF's locally you may be tempted to commit the generated file to your repository, especially if you intend to share your work online. However, this will lead to unnecessary large Git workspace and is not recommended. For this reason the `.gitignore`  file already ignores PDF files, and the upcoming exercise with GH Actions illustrates how a PDF can be generated online and saved as a downloadable artifact, rather than committing it to the repository.
```

(section:pdf-with-gha)=
## PDF output with GH Actions

Building and including your PDF is possible through a GitHub Action workflow that automatically builds the PDF when you push changes to GitHub. This has both is pros and cons. For instance, the build of your PDF is done prior to the build of your book, and if there is an error in the workflow your website may not be updated, or the PDF may not be included as a download. On the other hand, you do not need to install anything locally and the PDF is always up to date when you push changes. The most important reason for including the PDF build in your GHA workflow is that your PDF will be generated and included automatically as a downloadable file along with your website. You will learn to do this in several ways by the end of this lesson.

The workflow steps are:

```yaml
jobs:
  deploy:
    ...
    steps:
      ...
      - uses: typst-community/setup-typst@v4
      ...
    - name: Build PDF
      run: |
        jupyter book build --pdf

    - name: Upload Output PDF as Artifact
      uses: actions/upload-artifact@v4
      with:
        name: Output PDF
        path: exports/book.pdf
        compression-level: 0
```

````{exercise} Change the workflow

::::{tab-set} 
:::{tab-item} Locally

Using the example code provided above, update your `deploy.yml` file to build the PDF as part of your GitHub Action workflow.

Visit the Actions page of your repository to find where the artifact (PDF) can be downloaded.

```{hint}
Click on the last completed workflow run and look to the bottom of the page.
```
:::
:::{tab-item} Online

Using the example code provided above, update your `deploy.yml` file to build the PDF as part of your GitHub Action workflow.

Visit the Actions page of your repository to find where the artifact (PDF) can be downloaded.

```{hint}
Click on the last completed workflow run and look to the bottom of the page.
```
:::
::::
````

## Change the PDF template

Take a look at the PDF generated in the previous exercises using the `lapreprint-typst` template. You probably notice that it is does a good job at converting the website into a PDF document. However, you may have also noticed some text or formatting that isn't perfect, or perhaps you thought that you might want a cover page or table of contents for the PDF.

It turns out the `lapreprint-typst` template is not ideal for rendering content designed as a website made with the `book-theme`. Luckily, another Typst template is available: [the Plain Typst Book `plain_typst_book`](https://github.com/myst-templates/plain_typst_book) (not yet listed on the MyST Templates GH Organization). An example YAML snippet that implements this in the `myst.yml` file is illustrated here:

```yaml
  exports:
    - format: typst
      template: https://github.com/myst-templates/plain_typst_book.git
      output: exports/book.pdf
      id: output-pdf
```

````{exercise} Change the template

::::{tab-set} 
:::{tab-item} Locally

Using the example code provided above, update your `myst.yml` file to use the `plain_typst_book` template in your book, then rebuild the PDF.

Observe how the rendered PDF is different than the previous template.
:::
:::{tab-item} Online

Using the example code provided above, update your `myst.yml` file to use the `plain_typst_book` template in your book. After making a commit, wait for the workflow run to complete, then view the PDF after downloading it as an artifact.

Observe how the rendered PDF is different than the previous template.
:::
::::
````

## More fun with PDF's

Now that you have successfully created a PDF and changed the template, a few small exercises are provided here to illustrate how the template can be customized, as well as how the PDF can be included as a download via the _website._

You can complete the exercises in this section in any order.

### Customize the PDF output

The `plain_typst_book` template includes options that can be set by the user to customize how the PDF is generated. For example, `cover`, `logo` `logo_width` and `ToC_depth` are added to the `myst.yml` file.

```yaml
  exports:
    - format: typst
      template: https://github.com/myst-templates/plain_typst_book.git
      output: exports/book.pdf
      id: output-pdf
      cover: content/figures/logo.svg
      logo: content/figures/logo.svg
      logo_width: 5
      ToC_depth: 2
```

````{exercise} Add template options

::::{tab-set} 
:::{tab-item} Locally

Using the example code provided above, update your `myst.yml` file to customize the PDF output, then rebuild the PDF. Feel free to experiment with the images and parameters.
:::
:::{tab-item} Online

Using the example code provided above, update your `myst.yml` file to customize the PDF output. Feel free to experiment with the images and parameters.

Make a commit and download the artifact to view the change.
:::
::::
````

### Add Download PDF button to website

You may have noticed a large "Feedback" button at the top right of your website. This is one example of what Jupyter Book 2 (and MyST) refer to as "actions" (not the same as GitHub Actions!). It would be very useful to include a similar button for downloading the PDF of your book. This can be done by adding the following values to the `actions` sub-section of the `site` section in `myst.yml`:

```yaml
site:
  ...
  actions:
      ...
      - title: PDF
        url: ./exports/book.pdf
```

````{exercise} Add PDF Download button

::::{tab-set} 
:::{tab-item} Locally

Using the example code provided above, add a PDF download button. Once the `myst.yml` file has been updated the PDF must be regenerated and the website updated.

Confirm that this was done successfully by checking that the PDF button downloads the file properly.
:::
:::{tab-item} Online

Using the example code provided above, add a PDF download button. Once the `myst.yml` file has been updated the PDF must be regenerated and the website updated, which is done automatically once the commit is made.

Confirm that this was done successfully by checking that the PDF button downloads the file properly.
:::
::::
````

```{tip} Order matters!
Note that in order for the PDF to be included in the website, the PDF must be generated _before_ the website is built. When working locally, this means you need to run the build command before updating the website. For GitHub Actions, the PDF build step must be listed _above_ the HTML build step.
```