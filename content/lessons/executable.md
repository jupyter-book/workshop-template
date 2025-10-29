---
numbering:
  title:
    offset: 0
---

# Executable content

MyST supports a number of ways to include executable content in your project.

## Options

### Jupyter Notebook outputs

### Executing at build time
[kernel](https://docs.jupyter.org/en/latest/glossary.html#term-kernel)

### In page execution

## Installing Jupyter Server

## Adding a Jupyter Notebook

In this repository we have included a Jupyter notebook, which has been executed and includes outputs.

:::{exercise} Add a `.ipynb` file to the book
Add to ToC.
:::

:::{exercise} Execute at build time
Rerun with `--execute`
Make change
:::

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
