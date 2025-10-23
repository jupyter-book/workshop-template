---
numbering:
  title:
    offset: 0
  start: 7
---

(pdfoutput)=
# Create PDF output 🌶

Jupyter Book 2 is centered around creating interactive online documents. However, there are several instances when a PDF, next to the online book, is desired, for example:

- for use in note taking applications (e.g., students annotating a textbook chapter, or reviewing the draft of a website),
- if a printed copy of the book is required,
- to more easily carry out a plagiarism check.

One of the strengths of Jupyter Book 2 is the ease with which high-quality PDF's can be created from the same source files as an online book. To accomplish this, a [template](https://github.com/myst-templates) is used to create a PDF with a consistent look and feel between the two document formats. In addition, such templates can be customized to fit the specific needs of the documents being created.

This exercise provides an overview the PDF output capabalities of the Jupyter Book 2 and MyST ecosystem, accompanied by exercises to get you started creating your own PDF output (with Typst) using two different templates.

## PDF Generation: Typst and LaTeX

Jupyter Book 2 currently supports two primary ways to export your book as a PDF: LaTeX or Typst. Both are powerful tools for generating high-quality PDFs, but they differ in several key aspects (additional advantages and disadvantages [described here](https://mystmd.org/guide/creating-pdf-documents)):

| Feature            | Typst                                      | LaTeX                                      |
|--------------------|--------------------------------------------|--------------------------------------------|
| **Ease of Use**    | Modern syntax, easier to learn and use      | Steeper learning curve, more complex syntax|
| **Speed**          | Fast compilation                           | Slower compilation, especially for large docs|
| **Customization**  | Templates are easy to modify                | Highly customizable, but requires more effort|
| **Integration**    | Designed for MyST Markdown and Jupyter Book | Widely supported in academic publishing    |
| **Community**      | Growing, newer ecosystem                   | Large, established community               |
| **Features**       | Good support for math, figures, and tables | Extensive support for math, figures, tables, and packages|
| **Output Quality** | High-quality, modern look                   | Professional, traditional academic look    |

In short: choose Typst for simplicity and speed, or LaTeX for advanced customization and compatibility with academic standards.

Below we provide the screen shots of the PDF output using Typst (left) using the [plain_typst_template](https://github.com/myst-templates/plain_typst_book) and LaTeX (right) using the [plain_latex_template](https://github.com/myst-templates/plain_latex_book).

```{figure} figures/mystvstex.*
:width: 100%
:name: fig_mystvstex

Comparison of PDF output using Typst (left) and LaTeX (right) using both the plain book template.
```

You can specify the [output template](https://github.com/myst-templates), download the template and tweak to match your preferences. We won't go into detail here, but you can find more information [in the MyST Markdown documentations](https://mystmd.org/guide/creating-pdf-documents).

```{note}
One reason Typst is preferred in this workshop is that the installation (both for local users and via GitHub Actions) is much faster and easier than LaTeX, as you will see when we implement the PDF generation in our workflow file.
```

### Considerations

When starting your own project, consider whether a PDF output is desired. If so, consider the interactive elements that may be included and wether or not, some functionality and not all multimedia are supported in a PDF. For instance, a *.gif file cannot be included in a PDF. JB2 is thoughtful in this by choosing the best possible alternative if multiple files with the same name but different extensions are present: gif is chosen over png, png over jpg. Rather than specifying the extension, you can just use the file name and an asterisk, e.g. `![figure](figures/mystvstex.*)`.

For YouTube clips and online interactive materials embedded through iframes, you can make use of plugins. See for instance the [iframe-to-thumbnail plugin](https://github.com/jupyter-book/myst-plugins/tree/main/plugins/iframe-to-thumbnail-pdf). This plugin replaces the iframe with a thumbnail image that links to the original content as well as a QR code and a link in the caption.


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


## Excluding and including sections for PDF[^1]
[^1]: Directly copied from the official [Myst documentation](https://mystmd.org/guide/creating-pdf-documents#excluding-content-from-specific-exports).


If you need to inject some LaTeX or Typst-specific content into their respective exports, you may use the {raw:latex} or {raw:typst} role and directive. For example, to insert a new page in Typst with two columns:


```{raw:typst}
#set page(columns: 2, margin: (x: 1.5cm, y: 2cm),);
```

Or, 

`+++ { "page-break": true }` for a page break.



The content in these directives and roles will be included exactly as written in their respective exports, and will be ignored in all other contexts.

You may use block metadata to insert page breaks into your PDF or docx export with +++ { "page-break": true }. This will have no impact on your MyST site build nor other static exports that disregard “pages” (e.g. JATS).


+++{"no-pdf": true}
This won't be in the PDF.
+++

### Configure PDF output



### Typst

When exporting to Typst format, you can provide Typst-specific math content using the typst option. This allows you to use native Typst syntax instead of relying on tex-to-typst conversion, which may give incorrect results.

Example with typst argument in a math block:
https://mystmd.org/guide/math#typst-math
