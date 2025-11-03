---
numbering:
  title:
    offset: 0

kernelspec:
  name: python3
  display_name: 'Python 3'
---

# More content

In [](#fundamentals) we covered the basics of Jupyter Book structure and writing text content in markdown.
However, Jupyter Book can go far beyond basic text formatting and has tools to help you share information with figures, videos, special blocks, interactive elements and advanced cross-referencing.
In this lesson we will look at some of these features that elevate your book over a plain-text document.

## Directives and roles

This lesson will make use of [roles and directives](xref:myst-guide/syntax-overview#directives-roles).
These have a similar syntax, and are used to extend the basic markdown features.
The main difference is that roles are written in-line and take a single argument, whereas directives are multi-line containers which may have multiple arguments and options.

Both directives and roles use "fences", which are either (at least) three colons `:::` or backticks `` ``` ``.
You can use more colons or backticks to nest directives.
The [MyST documentation](xref:myst-guide/syntax-overview#directives-roles) explains the syntax, nesting and the difference between colons and backticks in more detail.

:::{note}
If there is a feature you would like to add to your project,
you could create a new role or directive in a plugin to extend the behaviour of MyST.
:::

## Images and figures

The quickest way to include an image is with the Markdown notation `![alt text](url-or-path)` as done below

```markdown
![External image](https://polslab.tnw.tudelft.nl/figures/training.JPG)
```
resulting in
![External image](https://polslab.tnw.tudelft.nl/figures/training.JPG)

However, this gives us limited options to customize the figure.
Moreover, we are dependent of a stable external URL.
We can include our own figures and add more options using the [`figure` directive](#cheat_sheet_figures).

If we want to add a figure to our book, we can use the URL of an external website (as in the figure above).
However, this carries the risk that the figure will no longer be visible if it is moved from its location.[^embeddingimages]
It is therefore better to have the figure as a local source file where you build the book.
We will do this by adding an image file to your git repository.

:::::{exercise} Include a figure
::::{tab-set}
:::{tab-item} GitHub
On GitHub, under the `code` tab…

1. Navigate to content/figures and click on `add file` $\rightarrow$ `Upload files`.

``` {figure} figures/incl_fig.*
:width: 100%
:name: fig_incl_fig

Add a file in the folder by choosing `Upload files`
```
2. Choose the figure you want to add (remember the file name!).
3. Commit your changes to GitHub (the file will be uploaded).
4. Navigate to the `book` folder and open `intro.md` and click `edit this file`.
5. Copy the code below into that file, and change the figure name to your own figure's name.

````{code} myst
``` {figure} figures/incl_fig.PNG
:width: 50%
:name: fig_myfirstfigure
add file in the folder
```
````

6. Commit your changes and view the result on GitHub pages.
:::
:::{tab-item} Locally
1. Put the image file you want to include to the `content/figures` folder on your computer.
2. Navigate to the `book` folder and open `intro.md`.
3. Copy the code below into that file, and change the figure name to your own figure's name.
````{code} myst
``` {figure} figures/incl_fig.PNG
:width: 50%
:name: fig_myfirstfigure
add file in the folder
```
````
4. Commit your changes and view the results.

```{hint}
Remember to add your image to the repository with `git add`.
```
:::
::::
:::::

```{warning}
The filename is case sensitive.
So it matters whether your extension is .png or .PNG.
You can also use .* to avoid this issue, the system will then pick the right extension where the best options is chosen first (*e.g.* .gif over .png, and .svg over .jpg).
This also avoids conversion issues for pdf output of non-static or non-supported formats
```

```{tip}
You can find more information about figure options [in the MyST documentation](xref:myst-guide/figures#figure-directive).
```

You can position figures in different places (left / center / right / margin), adjust the size, add a caption, _etc._.
Check the documentation above and try out the different settings.

## Embed a video (from YouTube)

We can embed videos hosting platforms like YouTube or Vimeo using the [iframe directive](xref:myst-guide/figures#youtube-videos).
For example, the following code embeds a video about Markdown,

````markdown
```{iframe} https://www.youtube.com/embed/dhzrlXzYOlU?si=n2U0HSJyotjp-r93
:width: 80%

Purves et al. - Jupyter Book 2 0 – A Next Generation tool for sharing for Computational Content
```
````

resulting in

```{iframe} https://www.youtube.com/embed/dhzrlXzYOlU?si=n2U0HSJyotjp-r93
:width: 80%

Purves et al. - Jupyter Book 2 0 – A Next Generation tool for sharing for Computational Content
```

```{note}
The use of iframe is not limited to videos.
You can embed content from other websites that support iframe embedding.
```

:::{note}
You can also use the `figure` directive to include a video from a local file, just like with images.
:::

```{tip}
There is a [plugin available](https://github.com/jupyter-book/myst-plugins/tree/main/plugins/iframe-to-thumbnail-pdf) that converts the YouTube clip in a qr code and a thumbnail for pdf exports.
```

```{exercise} Embed your own video
Embed a video of your choice using either the `iframe` or `video` directive.
You can use a YouTube video or any other video that supports embedding.
```

## Displaying code

You can display code using Markdown syntax.

````
```language
code
```
````

for example,

````
``` python
print("Hello world!")
```
````

renders as,

``` python
print("Hello world!")
```

You can also use the [`code` directive](xref:myst-guide/code#code-blocks) which will render the code in a block and has features line line numbers and captions.

:::{exercise} Add a code block
Take the following Python code snippet and put it in a code block with

- Python syntax highlighting
- Indicate the file name `fibonacci.py`
- Add a caption explaining that this function returns the `n`th number in the Fibonacci series

```
def fib(n):
    if n < 0:
        return
    if n in [0, 1]:
        return n
    else:
        return fib(n-2) + fib(n-1)
```
:::

## Diagrams

MyST supports displaying [Mermaid](https://mermaid.js.org/) diagrams using the [`mermaid` directive](xref:myst-guide/diagrams).
Mermaid let's you create a number of different types of diagrams using plain text.
This is a great way to show diagrams in your book, while keeping the source easily editable in version control.
For example, the following directive

````markdown
```{mermaid}
flowchart LR
  Start --> Stop

  A1(["Novice"]) --> B1
  A2(["I do know"]) --> B2 & B1
  B1(["Expert"])
  B2(["try"])

  A(["Start"]) --> B{"Decision"}
  B --> C["Option A"] & D["Option B"]
```
````

Renders as,

```{mermaid}
flowchart LR
  Start --> Stop

  A1(["Novice"]) --> B1
  A2(["I do know"]) --> B2 & B1
  B1(["Expert"])
  B2(["try"])

  A(["Start"]) --> B{"Decision"}
  B --> C["Option A"] & D["Option B"]
```

```{exercise} Create a diagram
Create your own mermaid diagram.
You can create a diagram from scratch, consulting the syntax in the [Mermaid documentation](https://mermaid.js.org/intro/),
or copy [an example](https://mermaid.js.org/syntax/examples)
```

## Admonitions

[Admonitions](xref:myst-guide/admonitions) can be used to separate text from the main text and highlight it appropriately.
Here are a set of admonitions built in to Myst,

`````{tab-set}

````{tab-item} Note
```{note}
This is an note admonition
```
````

````{tab-item} Important
```{important}
This is an important admonition
```
````

````{tab-item} Hint
```{hint}
This is an hint admonition
```
````

````{tab-item} See Also
```{seealso}
This is an seealso admonition
```
````

````{tab-item} Tip
```{tip}
This is an tip admonition
```
````

````{tab-item} Attention
```{attention}
This is an attention admonition
```
````

````{tab-item} Caution
```{caution}
This is an caution admonition
```
````

````{tab-item} Warning
```{warning}
This is an warning admonition
```
````

````{tab-item} Danger
```{danger}
This is an danger admonition
```
````

````{tab-item} Error
```{error}
This is an error admonition
```
````

`````

Custom admonitions can also be created in a plugin, but hiding the icon and adding your own icon in the title is a quick way to get a custom look.

````{myst}
```{warning} 🌶 HOTHOTHOT
:icon: false
:class: dropdown

This is a custom warning admonition with a custom icon, try changing it!
```
````

:::{exercise} Admonitions
Use an appropriate admonition to contain the following paragraphs.

Hand wash only

Syntax error

Beware of the leopard
:::

## Tabs, cards, grids

MyST has a number of features for arranging and organising content, you have already seen some of these following these lessons.

- [](xref:myst-guide/dropdowns-cards-and-tabs)
- [](xref:myst-guide/asides)
- [](xref:myst-guide/blocks)

Tabs can be used to separate content into different sections that can be viewed by clicking on the tab headers.
They are useful when you want to present a set of mutually exclusive options.

```markdown
:::: {tab-set}
::: {tab-item} Tab 1
Content for Tab 1
:::
::: {tab-item} Tab 2
Content for Tab 2
:::
::::
```

Renders as,

:::: {tab-set}
::: {tab-item} Tab 1
Content for Tab 1
:::
::: {tab-item} Tab 2
Content for Tab 2
:::
:::
::::

:::{exercise} Create a tab set for installing MyST
Put the following instructions for installing MyST into a tab set,
splitting instructions for `pip` and `npm` into different tabs.

Install MyST

*Using pip:* `pip install mystmd`

*Using npm:* `npm install -g mystmd`
:::

[^embeddingimages]: Fetching images from someone else's site also puts strain on their web server, which they may not appreciate.
