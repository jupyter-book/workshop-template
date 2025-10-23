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

## Include a figure

The quickest way to include a figure is by using `![](url)` as done below

```markdown
![External image](https://polslab.tnw.tudelft.nl/figures/training.JPG)
```
resulting in
![External image](https://polslab.tnw.tudelft.nl/figures/training.JPG)

This, however, gives us limited options to customize the figure. We can include more options using the [`figure` directive](#figures).

If we want to add a figure to our book, we can embed an URL to an external website (as in the figure above). However, this carries the risk that the figure will no longer be visible if it is moved from its location. It is therefore better to have the figure as a local source file.

So, we first need to upload a figure to GitHub and then refer to that figure in our file. 

```{note} 
This will become much easier later. Once you have cloned the repository to your local computer, you can simply add the figure file to the correct folder on your computer and push the changes to GitHub. 
```

`````{exercise} Include your first figure
::::{tab-set}
:::{tab-item} GitHub
On GitHub, under the `code` tab...

1. Navigate to content/figures and click on `add file` $\rightarrow$ `Upload files`.

```` {figure} figures/incl_fig.*
:width: 100%
:name: fig_incl_fig

Add a file in the folder by choosing `Upload files`
````
2. Choose the figure you want to add (remember the file name!).
3. Commit your changes to GitHub (the file will be uploaded).
4. Navigate to the `book` folder and open `intro.md` and click `edit this file`.
5. Copy the code below into that file, and change the figure name to your own figure's name.

````{code} myst
``` {figure} figures/incl_fig.PNG
---
width: 50%
name: fig_myfirstfigure
---
add file in the folder
```
````

6. Commit your changes and view the result on GitHub pages.
:::
:::{tab-item} Local
1. Add the figure file you want to include to the `content/figures` folder on your computer.
2. Navigate to the `book` folder and open `intro.md`.
3. Copy the code below into that file, and change the figure name to your own figure's name.
````{code} myst
``` {figure} figures/incl_fig.PNG
---
width: 50%
name: fig_myfirstfigure
---
add file in the folder
```
````
4. Save your changes and view the results.

:::
::::
`````

```{warning}
The code is case sensitive. So it matters whether your extension is .png or .PNG. You can also use .* to avoid this issue, the system will then pick the right extension where the best options is chosen first (e.g. .gif over .png, and .csv over .jpg). This also avoids conversion issues for pdf output of non-static or non-supported formats
```

```{tip}
We have a page with all important [codes](#cheatsheet).

You can find more information about figure options [here](https://mystmd.org/guide/figures).

```

You can position figures in different places (left / center / right / margin), adjust the size, add a caption, etc. Check the documentation above and try out the different settings.

## Embed video (from YouTube) using iframe or video
We can embed videos from YouTube using an iframe. For example, the following code embeds a video about Markdown:

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

You can also use the [`video` directive](https://mystmd.org/guide/figures#videos) to embed videos. 

```{note}
The use of iframe is not limited to YouTube videos. You can embed content from other websites that support iframe embedding.
```

```{tip}
There is a [plugin available](https://github.com/jupyter-book/myst-plugins/tree/main/plugins/iframe-to-thumbnail-pdf) that converts the YouTube clip in a qr code and a thumbnail for pdf exports.
```

```{exercise} Embed your own video
Embed a video of your choice using either the `iframe` or `video` directive. You can use a YouTube video or any other video that supports embedding.
```



## Include python code using code-block


```markdown
---
kernelspec:
  name: python3
  display_name: 'Python 3'
---
```

md -> kernel specification at frontmatter
```{code-cell} python
start = 1
next = 2

for i in range(5):
    print(f"{start} + {next} = {start + next}")
    start, next = next, start + next
```


## Directives

[Various directives](https://mystmd.org/guide/directives) are available. These follow the same syntax as figures. For example, we can include a mermaid diagram:

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

Resulting in:

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

```{exercise} Create your own directive
Create your own mermaid diagram or directive. For inspiration, see [these directives](https://mystmd.org/guide/directives) examples or [here](https://mystmd.org/guide/proofs-and-theorems).


```


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




## Tabs, cards, grids
We already made use of tabs in the exercises above. Tabs can be used to separate content into different sections that can be viewed by clicking on the tab headers.

```markdown
:::: {tab-set}
::: {tab-item} Tab 1
Content for Tab 1
:::
::: {tab-item} Tab 2
Content for Tab 2
:::
::: 
```
resulting in:
:::: {tab-set}
::: {tab-item} Tab 1
Content for Tab 1
:::
::: {tab-item} Tab 2
Content for Tab 2
:::
:::