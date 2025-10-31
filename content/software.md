(software)=
# Software

This page provides an overview of commonly used software, with limited instructions for using them. 

## Integrated Development Environment (IDE)

An IDE is required to complete many of the exercises in this workshop. Many of them could be completed in a simple text editor, however, an IDE that includes features such as version control with Git, environment management and a CLI would be useful. As such, the instructions herein often refer to Jupyter Lab. However, you can choose your own IDE, noting that the main requirements are dictated by the use of Jupyeter Notebook (`*.ipynb`) files:

- ability to edit notebooks natively (i.e., not editing the raw JSON),
- access to a Jupyter server and Python kernel for executing notebooks.

### Jupyter Lab

To run Jupyter Notebooks we can use IDE’s as Jupyter Notebook or Jupyter Lab. Jupyter Notebook is a web-based interface that allows users to create and share documents with live code, visualizations, and narrative text in a linear format. Jupyter Lab, on the other hand, is a more advanced interface offering a flexible and modular environment with multiple panels, including notebooks, terminals, and text editors, providing a more versatile experience for interactive computing. I prefer to use Jupyter lab.

### GitHub web-based editor

The github.dev web editor makes it possible to edit files directly in the browser. This is an excellent option if you are unable to install software on your computer. To activate it, simply navigate to a GitHub repository and press `.`. It's really that easy!

```{tip}
Note that while this IDE can be used for many of the exercises in this workshop, and you can _edit_ Jupyter Notebook files, you will _not_ be able to use iexecute notebooks directly in the browser (however, notebooks will be executed during build in the GitHub Actions workflow).
```

You can find out more about this useful tool [here](https://docs.github.com/en/codespaces/the-githubdev-web-based-editor).

### VSC
A popular code editor is [Visual Studio Code](https://code.visualstudio.com/) (VSC). It allows you to program in different languages, where it recognizes the commands in that language and adjusts the FONT so that it becomes better readable. Moreover, it allows you to install various packages (such as Jupyter Notebook). It also integrates GIT and allows to code using Co-Pilot, an AI pair programmer. We advise to use VSC as it allows for multiple programming languages. 

#### Terminal
The terminal in VSC is a tool that lets you interact with your computer's command line directly within the editor. It's used to run commands, scripts, or programs without leaving the coding environment. For example, you can compile code, run a development server, install dependencies, or manage files. It's very helpful for developers because it allows you to code and execute commands in one place, streamlining your workflow.

```{figure} figures/VSCterminal.*
---
name: fig_VSCterminal
width: 100%
---
The VSC terminal to interact with the computer using the command line
```

#### Extensions
Extensions in Visual Studio Code (VSC) are powerful add-ons that enhance the functionality of the editor by providing additional features, tools, and support for various programming languages, frameworks, and technologies. Extensions allow you to customize and tailor VSC to suit your specific development needs.

##### How to Install Extensions:
- Access Extensions View:
    * Click on the Extensions icon in the Activity Bar on the side (or press Ctrl+Shift+X / Cmd+Shift+X).

- Search for Extensions:
    * In the Extensions view, you can search for the name or keywords related to the extension you want to install.

- Install the Extension:
    * Click the Install button on the desired extension, and it will automatically be added to VSC.

- Manage Installed Extensions:
    * You can view, enable, disable, or uninstall extensions from the same Extensions view.

##### Popular Extensions in VSC:
* Python: Provides linting, debugging, IntelliSense, and more for Python development.
* Jupyter: Provides support for Jupyter notebooks within VSC.
* Arduino: Provides support for programming in Arduino.
* Code Spell Checker: Has a great spelling checker, also available for Dutch
* Github Copilot: Your AI pair programmer. Helps you in writing code.
* LaTeX workshop: LaTeX coding, preview, compiling.
* MyST-Markdown: The official Markdown syntax extension


## Requirements.txt

A `requirements.txt` file is included for this workshop that contains the basic dependencies needed to complete it. Note in particular that 

We included a [requirements.txt](../..requirements.txt) file with all dependencies that are likely to be used.
These include:
| Package | Description |
|---|---|
| jupyter-book>=2.0.0a0 | Tool to build publication-quality books and documentation from Jupyter notebooks and Markdown. |
| jupyterlab | Web-based interactive development environment for notebooks, code, and data. |
| mystmd | MyST Markdown support for Jupyter Book / Sphinx (optional / commented). |
| jupyterlab_myst | JupyterLab extension to render MyST Markdown and improve notebook/Markdown integration. |
| ipykernel | IPython kernel for Jupyter, enables running Python code in notebooks. |
| ipywidgets | Interactive HTML widgets for Jupyter notebooks and JupyterLab. |
| numpy | Core library for numerical computing with arrays and linear algebra. |
| matplotlib | 2D plotting library for generating figures and visualizations. |
| scipy | Scientific computing library (optional / commented). |

If you are sure you want to install these dependencies, download the file, navigate through the correct folder and use `pip install -r requirements.txt`.

## Typst
For this template we use Typst to produce a high quality pdf. If you want to create pdf's locally, you'll have to install Typst. Follow the [Typst installation instructions](https://github.com/typst/typst?tab=readme-ov-file#installation) for several options to install Typst. We strongly recommend using the latest releases of Typst. If you get a confusing Typst error, a good first step is to upgrade your version of Typst.
