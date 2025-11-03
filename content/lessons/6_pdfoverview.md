---
numbering:
  title:
    offset: 0
  start: 7
---

(pdfoutput)=
# Create PDF output 🌶

Jupyter Book is centered around creating interactive online documents. However, there are several instances when a PDF, next to the online book, is desired, for example:

- for use in note taking applications (e.g., students annotating a textbook chapter, or reviewing the draft of a website),
- if a printed copy of the book is required,
- to more easily carry out a plagiarism check.

One of the strengths of Jupyter Book 2 is the ease with which high-quality PDF's can be created from the same source files as an online book. To accomplish this, a _template_ is used to create a PDF with a consistent look and feel between the two document formats. In addition, such templates can be customized to fit the specific needs of the documents being created.

This lesson provides an overview the PDF output capabilities of the Jupyter Book 2 and MyST ecosystem, accompanied by exercises to get you started creating your own PDF output (with Typst) using two different templates. The following pages:

1. introduce document generation with MyST (including an explanation of templates),
2. present an overview and comparison of PDF generation with Typst and LaTeX, and
3. provide exercises to generate a PDF with a Typst template, both locally and using GitHub Actions.