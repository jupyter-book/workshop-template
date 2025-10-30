---
numbering:
  title:
    offset: 1
---

# Create a PDF 🌶

Now that you have an understainding of document creation using MyST and our choice to use Typst for PDF generation, you are ready to create a PDF from your book repository using Jupyter Book.

## Local PDF Output

### Install Typst and generate a PDF

**WIP**

:::{exercise} Confirm Typst installation
**WIP**
Run

```console
typst --version
```
:::

### Generate a PDF output with Typst

You can build the PDF locally using the command line:

```console
jupyter book build --typst
```

:::{exercise} Generate a PDF using the CLI
**WIP**
--> set back to lapreprint Typst template
- generate a PDF using the command line
- answer questions (bullet list below)
- look at the output. Can we do better? (yes)

The template is...
The PDF is found...

:::

### Change the PDF template

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


:::{exercise} Change the PDF template
**WIP**
change, view output
:::

:::{exercise} Explore Typst templates
visit the repo, read doc, change some features of the template
:::

## PDF output with GH Actions

Building and including your PDF is possible through a GitHub action that automatically builds the PDF when you push changes to GitHub. This has both is pros and cons. For instance, the build of your PDF is done prior to the build of your book. If there is an error in your book, the PDF AND your book will not be built. On the other hand, you do not need to install anything locally and the PDF is always up to date when you push changes.

```{warning}
The GitHub workflow this only works when there are no errors in the markdown files.
For instance, it breaks when figures are missing.
```

There is a third option where you have a separate PDF build github action that only builds the PDF when you push to a specific branch, e.g. `main` or `release` or when you initialize the workflow yourselves.

```yaml
    # Install Typst for PDF generation
    - name: Install Typst
      run: |
        typst --version

    # Build the PDF using Typst
    - name: Build PDF
      run: |
        myst build --typst
```

```{tip} Good practice with PDFs and Git
Don't commit PDF's. Hence the `.gitignore`. Don't let your GHA commit PDF's either (hence the artifact upload, which is shown later).
In fact, PDF generation in GHA is a form of software testing: successful generation of the PDF indicates everything is working properly.
```

:::{exercise} Add PDF generation to GHA workflow
**WIP**
change, view output
:::

## More fun with PDF's

add MyST action button, add download on page.

Upload as artifact (GHA only). This can be done even if the website build fails.
