---
numbering:
  title:
    offset: 0
kernelspec:
    name: python3
    display_name: 'Python 3'
---

# Executable content introduction

MyST supports a number of ways to include executable content in your project.

```{tip}
Instructions are provided here for Jupyter Lab, however, you can use any IDE you are comfortable with. An explanation is provided on the [Software](#software) page.
```

## Installing Jupyter

Executable content in MyST is processed by a [Jupyter](xref:jupyter) server and appropriate [kernel](https://docs.jupyter.org/en/latest/glossary.html#term-kernel).
In this lesson, we will run a local Jupyter server to execute code cells.

A pip requirements file, `requirements.txt` in the root of the repository specifies all of the dependencies you need.
You can install all of these in a virtual environment using `pip` and then launch Jupyter.

::::{tab-set}
:::{tab-item} Linux and MacOS
```console
python3 -m venv ./venv
source ./venv/bin/activate
pip install -r requirements.txt
jupyter lab
```
:::
:::{tab-item} Windows
```console
python -m venv venv
```

For Command Prompt

```console
venv\Scripts\activate.bat
```

For PowerShell

```console
venv\Scripts\activate.ps1
```

Then

```console
pip install -r requirements.txt
jupyter lab
```
:::
::::

This will automatically open the Jupyter Lab interface (at [localhost:8888](http://localhost:8888)) in your browser, which we will use later.

```{tip} Using GitHub actions
One can use GitHub Actions to execute content at build time on GitHub servers as well, see an example `deploy.yml` [below](#GHA-example). More on the GitHub actions in the next lesson.
```

## Options

### Jupyter Notebook outputs

MyST can use Jupyter notebooks, `.ipynb` files, as input just like Markdown.
If you have a notebook which you have executed, you can add it to the book.
Markdown cells will be rendered in exactly the same way as a Markdown file.
So you can use all of the MyST Markdown you have already learned.
Outputs such as images and interactive plots will also be rendered in the book.

(label-notebooks)=
Blocks can be labelled, either by editing a cell's JSON metadata, or with the following syntax,

```python
#| label: my-label
```

Labels are particularly useful when integrating notebooks into larger documents such as theses or technical reports. By assigning labels to code blocks, and their corresponding outputs, you can reference them directly within your text, making it clear which code produced which figure, table, or result. [This example](https://luukfroling.github.io/BEP/#visualisation-reconstruction) makes use of labels to reference figures from the Python notebook.

:::{note}
This is the syntax for Python, where `#` is the comment character.
For other languages, the syntax is the comment character followed by `|`.
In Javascript, for example, the above label would be,

```
//| label: my-label
```
:::

Figures can be given a caption in a similar way,

```python
#| caption: Caption text
```

We will explore using Jupyter notebooks as input for MyST in [](#lesson-exec-jupyternb).

### Executing at build time

MyST can also execute content at build time, through connecting to a Jupyter server.
Executable cells can be in the `.ipynb` format as well as written in Markdown using either the [`code-cell` directive](xref:myst-guide/notebooks-with-markdown#code-cell) or [`eval` role](xref:myst-guide/notebooks-with-markdown#myst-inline-expressions).

We will cover executing at build time with Jupyter Notebooks in [](#lesson-exec-jupyternb), and with Markdown in [](#lesson-exec-markdown).

### In page execution

Through connecting your site to a remote Jupyter, it is also possible to execute code cells live, in the browser.
This feature is excellent for presenting readers with interactive elements, such as data science workflows they can follow along, or exercises where they are invited to change code.

In page execution is not covered in this lesson.

(lesson-exec-jupyternb)=
## Adding a Jupyter Notebook

In this repository we have included a Jupyter notebook, `example.ipynb`, which has been executed and includes outputs.

:::{exercise} Add a `.ipynb` file to the book
Add the example notebook to the book by giving it an entry in the table of contents in `myst.yml`.
Rebuild the book and look at the new page.
:::

:::{exercise} Make changes
Navigate to [your Jupyter Lab instance](http://locahost:8888).
Make some changes to the notebook.
Try adding,

1. Markdown cells
2. Code cells in Python

Rerun the entire notebook by clicking "Run" -> "Restart Kernel and Run All Cells…"
Rebuild the book and look at your changes.
:::

::::{exercise} Execute at build time
Instead of running the notebook in Jupyter Lab, you can also execute the notebook as the book is built.
To do this, run,

```console
myst start --execute
```

:::{hint}
If you installed Jupyter in a virtual environment, like we recommended above, you will need to run myst in that environment so that a Jupyter server can be launched.

```console
source ./venv/bin/activate
myst start --execute
```
:::

Now, make changes to the notebook and save it **without** running the cells.
You will see MyST detect the notebook has been changed and re-run it automatically.
::::

(lesson-exec-markdown)=
## Executable Markdown

Unlike Jupyter notebook files, Markdown files do not store the output of executions.
This means to include the outputs in our project, we must execute the cells at build time.
To make a Markdown file executable, you must first add a `kernelspec` to the files [frontmatter](xref:myst-guide/frontmatter).
For example, in this page,

```yaml
---
kernelspec:
    name: python3
    display_name: 'Python 3'
---
```

:::{tip}
The MyST Guide has a section on [the advantages of the `.md` and `.ipynb` formats](xref:myst-guide/md-vs-ipynb).
:::

You can add a block of executable code using the [`code-cell` directive](xref:myst-guide/notebooks-with-markdown#code-cell).
The directive has the format,

```markdown
:::{code-cell} <language>
:key: value
<code>
:::
```

The key/value pairs allow you to tag the cell in the same way as [with `ipynb`](#label-notebooks).

::::{exercise} Code cells
:::{note}
We will use the default Python kernel in these examples.
However, you can use another kernel, such as Javascript, R or Julia [by changing the page frontmatter and updating code cell blocks](xref:myst-guide/notebooks-with-markdown#use-a-different-kernel).
:::

Put the following Python snippet in a code cell.

```python
def fib(n):
    if n < 0:
        return
    if n in [0, 1]:
        return n
    else:
        return fib(n-2) + fib(n-1)


for i in range(10):
    print(i, fib(i))
```

Rebuild the book (with the `--execute` flag) and look at the result.

Now, add a `label` (using the key/value notation) to the code cell and reference it [here](x).
Make the code cell a figure by adding a `caption`; notice how the reference changes.
::::

You can also use the [`eval` role](xref:myst-guide/notebooks-with-markdown#myst-inline-expressions) to execute expressions in Markdown text.

::::{exercise} Inline execution
Copy the following examples using the `eval` role and complete the statements to execute.

```markdown
$6872 \times 3409$ is {eval}``

The first 15 multiples of 23 are {eval}``
```

:::{hint}
For the second example, you may want to use a [list comprehension](https://docs.python.org/3/tutorial/datastructures.html#list-comprehensions).
:::
::::

## Cell Tags and Hiding Input

[Cell tags](xref:myst-guide/notebook-configuration#notebook-cell-tags) in Jupyter Notebooks are metadata labels that you can assign to individual cells.
They are useful for customizing the behavior of cells, such as hiding code input.
Markdown cells allow you to add tags as well, e.g. `:tags: [hide-input]`.

To hide the input of a code cell (so only the output is visible), you can add a tag like `hide_input` to that cell.
JB2 recognizes this tag and will hide the code input when rendering or exporting the notebook. 

To add a tag:

1. Select the cell.
2. Open the "View" menu and enable the "Cell Toolbar" → "Tags".
3. Add the tag `hide_input` (or another tag recognized by your toolchain).

This feature is especially useful for creating clean, reader-friendly notebooks where you want to focus on results rather than code details, see below. 


```{code-cell} python
:tags: [hide-input]

print("This is the output of the cell, but the input code is hidden.")
```

```{exercise} Remove input
Create a code cell that calculates the square of numbers from 5 to 8 and prints the results.
Remove the input code from being displayed by adding the appropriate tag.
```

(GHA-example)=
## GitHub Actions Example

Here is an example GitHub Action workflow file to illustrate one possible way to build a virtual environment and execute notebooks during the book build. We will cover other aspects of the workflow file in later lessons (for example, GH Actions itself and PDF generation).

````{tip} GitHub Action workflow example
:class: dropdown

:::{code} yaml
name: MyST GitHub Pages Deploy
on:
  push:
    branches: [main]
env:
  # `BASE_URL` determines the website is served from, including CSS & JS assets
  # You may need to change this to `BASE_URL: ''`
  BASE_URL: /${{ github.event.repository.name }}

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: 'pages'
  cancel-in-progress: false
jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Setup Pages
        uses: actions/configure-pages@v3
      - uses: actions/setup-node@v4
        with:
          node-version: 18.x
      - uses: typst-community/setup-typst@v4

    # Install Python and dependencies
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'   # or your version

      - name: Install Python dependencies
        run: |
          python -m pip install --upgrade pip
          if [ -f requirements.txt ]; then pip install -r requirements.txt; fi
          pip install jupyter-server nbclient nbformat ipykernel jupyter-client
          # pip install plotly kaleido          
          python -m ipykernel install --user --name=python3
          
    # Install MyST 
      - name: Install MyST Markdown
        run: npm install -g mystmd
      
    # Build PDF
      - name: Build PDF
        run: |
          myst build --pdf

      - name: Upload Output PDF as Artifact
        uses: actions/upload-artifact@v4
        with:
          name: Output PDF
          path: exports/book.pdf
          compression-level: 0
    
          # Build book
      - name: Build execute 
        run: myst build --execute --html

      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: './_build/html'
          
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
:::
````