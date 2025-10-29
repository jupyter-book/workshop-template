---
numbering:
  title:
    offset: 0
---

# Executable content introduction

MyST supports a number of ways to include executable content in your project.

## Installing Jupyter

Executable content in MyST is processed by a [Jupyter](xref:jupyter) server and appropriate [kernel](https://docs.jupyter.org/en/latest/glossary.html#term-kernel).
In this lesson, we will run a local Jupyter server to execute code cells.

A pip requirements file, `requirements.txt` in the root of the repository specifies all of the dependencies you need.
You can install all of these in a virtual environment using `pip` and then launch Jupyter.

```console
python3 -m venv ./venv
source ./venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

This will automatically open the Jupyter Lab interface (at [localhost:8888](http://localhost:8888) in your browser, which we will use later.

## Options

### Jupyter Notebook outputs

MyST can use Jupyter notebooks, `.ipynb` files, as input just like Markdown.
If you have a notebook which you have executed, you can add it to the book.
Markdown cells will be rendered in exactly the same way as a Markdown file.
So you can use all of the MyST Markdown you have already learned.
Outputs such as images and interactive plots will also be rendered in the book.

Blocks can be labelled, either by editing a cell's JSON metadata, or with the following syntax,

```python
#| label: my-label
```

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

### Executing at build time

### In page execution

## Adding a Jupyter Notebook

In this repository we have included a Jupyter notebook, `example.ipynb`, which has been executed and includes outputs.

:::{exercise} Add a `.ipynb` file to the book
Add the example notebook to the book by giving it an entry in the table of contents in `myst.yml`
Rebuild the book and look at the new page.
:::

:::{exercise} Make changes
Navigate to [your Jupyter Lab instance](http://locahost:8888).
Make some changes to the notebook.
Try adding

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

## Executable Markdown

Unlike Jupyter notebook files, Markdown files do not store the output of executions.
This means to include the outputs in our project, we must execute the cells at build time.

:::{tip}
The MyST Guide has a section on [the advantages of the `.md` and `.ipynb` formats](xref:myst-guide/md-vs-ipynb).
:::

::::{exercise} Code cells

:::{tip}
We will use the default Python kernel in these examples.
However, you can use another kernel, such as Javascript, R or Julia [by changing the page frontmatter and updating code cell blocks](xref:myst-guide/notebooks-with-markdown#use-a-different-kernel).
:::
::::

:::{exercise} Inline execution
:::

## In page execution
