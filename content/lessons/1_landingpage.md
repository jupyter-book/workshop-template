---
numbering:
  title:
    offset: 0


site:
  hide_outline: true
  hide_toc: true
  hide_title_block: true

no-update-date: true
---
(landingpage)=
# Create your own landing page

+++ { "kind": "split-image" }
# Create your landing page
a great way to welcome your visitors and provide clear directions.

{button}`Check out the full documentation <https://mystmd.org>`

![](../figures/delft.png)

+++



A landing page is the first page that a visitor of your website will see. Hence, you want to make sure it has the right vibe and contains the right information. As in books, the cover can be set differently than its content. 

In Jupyter Book you have the option to:
- create a custom [landing page](https://jupyter-book.github.io/example-landing-pages/) using a split image.
- create sections using [blocks](https://mystmd.org/guide/blocks#blocks)
- hide [table of contents](https://mystmd.org/guide/website-navigation#hide-the-primary-sidebar)
- add a [custom footer](https://mystmd.org/guide/website-navigation#style-your-footer).
- add [cards](https://mystmd.org/guide/dropdowns-cards-and-tabs#cards) in a grid to link to specific pages or other websites.


+++ {"kind": "justified"}
## Hide outline and table of contents
To use the full width of the page, you can hide the outline and table of contents by including the following in your index.md (if that is the landing page):

```markdown
---
site:
  hide_outline: true
  hide_toc: true
  hide_title_block: true
---
```

As we make use of the [page-last-updated plugin](https://jupyter-book.github.io/myst-plugins/page-last-updated/), we also set `no-update-date: true` to hide the date of the last update.
+++

## Create specific blocks
You can create specific blocks which are styled differently. For instance, we used split-image at the top of the page. And `justified` for the [section on hiding the outline and table of contents](#hide-outline-and-table-of-contents). 

To create a *split image* on your landing page, you can use the `split-image` directive. This allows you to have an image on one side and text on the other side. You can customize the content and layout to fit your needs, e.g. include a button that links to some other page or website.

```markdown

+++ { "kind": "split-image" }

# Create your landing page

a great way to welcome your visitors and provide clear directions.

{button}`Check out the full documentation <https://mystmd.org>`

![](../figures/delft.png)

+++
```

In a similar we used the justified block which creates a block that spans the full width of the screen: 
```markdown
+++ {"kind": "justified"}
```

## Cards

Often cards are used at the landing page to link to specific pages or websites. For instance, using the justified: 

+++ {"kind": "justified"}

## Get started

````{grid} 2
```{card}
:header: 📖 Manual
:link: https://mystmd.org/guide

Read the manual where we describe the process of building and publishing a JupyterBook, including the necessary tools and resources.
```

```{card}
:header: ✍ Starterkit
:link: https://tud-jb-os.github.io/starterkit/

A TU Delft starterkit to help you get started with creating your own JupyterBook
```


```{card}
:header: 📈 Jupyter Book
:link: https://jupyterbook.org/

See the official Jupyter Book documentation for more information on how to use Jupyter Book and its features.
```


```{card}
:header: 🌅 Gallery
:link: https://jupyterbook.org/gallery/

See the collection of interactive textbooks published 
```

````

+++

+++ {"kind": "justified"}
## Gallery of landing pages
Below is a selection of landing pages created by the Jupyter Book community. You can use these for inspiration when creating your own landing page.

````{grid} 2
```{card}
:header: mystmd
:link: https://mystmd.org/

The official documentation of MyST
```
```{card}
:header: Jupyter Book
:link: https://jupyterbook.org/

The official documentation of Jupyter Book
```
```{card}
:header: personal website
:link: https://polslab.tnw.tudelft.nl

A personal website
```
```{card}
:header: Educational book
:link: https://topocondmat.org/

Landing page of an educational book.
```
````
