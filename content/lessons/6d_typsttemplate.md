---
numbering:
  title:
    offset: 1
---

# Working with the template

This page provides additional information about the [Typst template `plain_typst_book`](https://github.com/myst-templates/plain_typst_book) which was set up for this book as part of the exercises on the previous page. 

**WIP**
- brief overview of how the template works (repo, inclusion, etc)
- summary of how to "view" it
- examples of usage (options)
- more advanced explanations, if needed


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

When exporting to Typst format, you can provide Typst-specific math content using the typst option.
This allows you to use native Typst syntax instead of relying on tex-to-typst conversion, which may give incorrect results.

Example with typst argument in a math block:
https://mystmd.org/guide/math#typst-math
