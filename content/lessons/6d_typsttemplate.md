---
numbering:
  title:
    offset: 1
---

# Working with the template

_This is a partially completed file that gives some information about the template, but was not included in the workshop._

This page provides additional information about the [Typst template `plain_typst_book`](https://github.com/myst-templates/plain_typst_book) which was set up for this book as part of the exercises on the previous page.

An introduction to the template and it's features is provided on the `README.md` of the repository. In addition, an example book is built using a GitHub Actions workflow similar to what was created as part of the exercises on the previous page. It is deployed at [myst-templates.github.io/plain_typst_book/](https://myst-templates.github.io/plain_typst_book/) and illustrates how the PDF can be included as a downloadable file from the website. The source code is located in the `example/` directory, and is intended to serve as a reference for using the template.


## Excluding and including sections for PDF[^1]
[^1]: Directly copied from the official [Myst documentation](https://mystmd.org/guide/creating-pdf-documents#excluding-content-from-specific-exports).


If you need to inject some LaTeX or Typst-specific content into their respective exports, you may use the {raw:latex} or {raw:typst} role and directive.
For example, to insert a new page in Typst with two columns:


```{raw:typst}
#set page(columns: 2, margin: (x: 1.5cm, y: 2cm),);
```

Or, 

`+++ { "page-break": true }` for a page break.



The content in these directives and roles will be included exactly as written in their respective exports, and will be ignored in all other contexts.

You may use block metadata to insert page breaks into your PDF or docx export with `+++ { "page-break": true }`.
This will have no impact on your MyST site build nor other static exports that disregard “pages” (e.g. JATS).

```{note}
+++{"no-pdf": true}
This won't be in the PDF.
+++
```

## Typst

When exporting to Typst format, you can provide Typst-specific math content using the Typst option.
This allows you to use native Typst syntax instead of relying on tex-to-typst conversion, which may give incorrect results.

Example with Typst argument in a math block:
https://mystmd.org/guide/math#typst-math
