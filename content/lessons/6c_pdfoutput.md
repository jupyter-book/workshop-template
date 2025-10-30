---
numbering:
  title:
    offset: 1
---

# Create a PDF 🌶

**WIP**

- install Typst (local and GHA with tab-set)
- set up and build book as PDF with lapreprint Typst template
- look at output
- set up and build book with plain_typst_template
- look at output
- explain/illustrate setup: not committing PDF to repo; build in - GHA as a form of software testing
- set up extra stuff: add MyST action button, add download on page, upload as artifact (GHA only)




## Export through GitHub actions or locally

We specified in the `myst.yml` file that we want to export to PDF using Typst.
You can also choose LaTeX.
See the `myst.yml` file, or [](#code_export) for the syntax.

:::{literalinclude} ../../myst.yml
:start-after: exports
:end-at: ToC_depth: 2
:lineno-match:
:caption: Example of the export section in the `myst.yml` file, the book will be written to `exports/book.pdf`.
:label: code_export
:::


### Local build
When  both [myst](https://mystmd.org/guide/installing) and [typst](https://mystmd.org/guide/creating-pdf-documents#typst-install) are installed, you can build the PDF locally using the command line:

```console
myst build --typst
```

The book will be built in the `exports` directory as specified in the `myst.yml` file and the build files will be in the `_build` directory.


### GH actions
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
