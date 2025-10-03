---
kernelspec:
  name: python3
  display_name: 'Python 3'
---

# Lesson 2: Include awesomeness

## Embed video from YouTube using iframe or video


## Include figure

A figure sometimes says more than 1000 words...

![External image](https://polslab.tnw.tudelft.nl/figures/training.JPG)

If we want to add a figure to our book, we can refer to another website (as in the figure above). However, this carries the risk that the figure will no longer be visible if it is moved from its location. It is therefore better to have the figure as a local source file.

So, we first need to upload a figure to GitHub and then refer to that figure in our file. (Note! This will become much easier later.)

`````{exercise}
On GitHub, under the `code` tab...

1. Navigate to book/figures and click on `add file` $\rightarrow$ `Upload files`.

```` {figure} ../figures/blank.png
<!-- ```` {figure} figures/incl_fig.PNG -->
---
width: 50%
---
add file in the folder
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

````{tip}
We have a page with all important [codes](#cheatsheet).

You can find more information about figure options [here](https://teachbooks.io/manual/basic-features/figures.html).

```{warning}
Do we want references to teachbooks? It seems a bit messy to not refer to the official documentation. Moreover, some of the features may deprecated in the future.
```
````

You can position figures in different places (left / center / right / margin), adjust the size, add a caption, etc. Check the documentation above and try out the different settings.

## Include python code using code-block

md -> kernel specification at frontmatter
```{code-cell} python
start = 1
next = 2

for i in range(5):
    print(f"{start} + {next} = {start + next}")
    start, next = next, start + next
```