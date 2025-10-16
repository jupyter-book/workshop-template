---
numbering:
  title:
    offset: 0

kernelspec:
  name: python3
  display_name: 'Python 3'
---

# Include awesomeness

We have covered the basics of building text files in markdown. However, we can include figures,  

## Include a figure

A figure sometimes says more than 1000 words...

![External image](https://polslab.tnw.tudelft.nl/figures/training.JPG)

If we want to add a figure to our book, we can refer to another website (as in the figure above). However, this carries the risk that the figure will no longer be visible if it is moved from its location. It is therefore better to have the figure as a local source file.

So, we first need to upload a figure to GitHub and then refer to that figure in our file. (Note! This will become much easier later.)

`````{exercise}
On GitHub, under the `code` tab...

1. Navigate to content/figures and click on `add file` $\rightarrow$ `Upload files`.

```` {figure} figures/incl_fig.*
:width: 100%
:name: fig_incl_fig

Add a file in the folder by choosing `Upload files`
````
2. Choose the figure you want to add (remember the file name!).
3. Commit your changes to GitHub (the file will be uploaded).
4. Navigate to book and open `intro.md` and click `edit this file`.
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

6. Commit your change and view the result on GitHub pages.

`````

```{warning}
The code is case sensitive. So it matters whether your extension is .png or .PNG. You can also use .* to avoid this issue, the system will then pick the right extension where the best options is chosen first (e.g. .gif over .png, and .csv over .jpg). This also avoids conversion issues for pdf output of non-static or non-supported formats
```

```{tip}
We have a page with all important [codes](#cheatsheet).

You can find more information about figure options [here](https://mystmd.org/guide/figures).

```

You can position figures in different places (left / center / right / margin), adjust the size, add a caption, etc. Check the documentation above and try out the different settings.

## Embed video from YouTube using iframe or video



## Include python code using code-block

md -> kernel specification at frontmatter
```{code-cell} python
start = 1
next = 2

for i in range(5):
    print(f"{start} + {next} = {start + next}")
    start, next = next, start + next
```


## Directives

Various directives are available. These follow the same syntax as figures. For example, we can include a mermaid diagram:

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



```{mermaid}
flowchart LR
  subgraph inputs [ ]
    Start
    Novice
    Expert
  end

  Start --> B(["Choose path"]) --> Stop
  Novice --> A1(["GitHub Account"]) -->  B2 & B1(["Clone template"]) -->  Stop
  Expert --> A2(["GitHub Account"]) --> B2(["Install software"]) --> B1 & C2(["myst start"]) -->  Stop
```



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


```{mermaid} example
graph LR
    A1 --> midA1B1(( )) --> B1
    A2 --> B2
    midA1B1 --> B2
```
