---
numbering:
  title:
    offset: 1
---

# MyST Document Creation 🌶

Jupyter Book 2 (JB2) supports both [Markdown](https://en.wikipedia.org/wiki/Markdown) files and [Jupyter Notebooks](https://en.wikipedia.org/wiki/Project_Jupyter#Jupyter_Notebook) as content sources. 

## Markdown
Markdown is a simple markup language: plain text that is *formatted* with small pieces of 'code'. This allows you to create rich, interactive books that combine text, code, and visualizations. This text can then be quickly exported to various other formats such as PDF, Word, HTML, etc.

```{figure} ../figures/MyST.PNG
:width:80%

Documents made in MyST Markdown can be converted to many different formats. These can be saved as JSON, or rendered to a website (like this one!) or any number of formats including [PDF & LaTeX](https://mystmd.org/guide/creating-pdf-documents), [Word](https://mystmd.org/guide/creating-word-documents), [React](https://mystmd.org/guide/quickstart-myst-documents), or [JATS](https://mystmd.org/guide/creating-jats-xml). Picture taken from the MYST documentation [^MYST].
```

[^MYST]: https://mystmd.org/guide/

See below for an example of the Markdown language and how it is rendered in JB2.

`````{tab-set}
:::: {tab-item} rendered
# This is a heading
This is a paragraph with **bold** and *italic* text.
- This is a list item
- Another list item
```{warning} raw HTML
You can also include raw HTML in your Markdown files, but this will not be rendered in the PDF output.
```
::::
:::: {tab-item} markdown
````markdown
# This is a heading
This is a paragraph with **bold** and *italic* text.
- This is a list item
- Another list item
```{warning} raw HTML
You can also include raw HTML in your Markdown files, but this will not be rendered in the PDF output.
```

````
::::
`````

In the next chapter we cover most of the basic Markdown syntax you will need to create your own content.

