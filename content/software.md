(software)=
# Software

## VSC
A popular code editor is [Visual Studio Code](https://code.visualstudio.com/). It allows you to program in different languages, where it recognizes the commands in that language and adjusts the FONT so that it becomes better readable. Moreover, it allows you to install various packages (such as Jupyter Notebook). It also integrates GIT and allows to code using Co-Pilot, an AI pair programmer. We advise to use VSC as it allows for multiple programming languages. 

### Terminal
The terminal in Visual Studio Code (VSC) is a tool that lets you interact with your computer's command line directly within the editor. It's used to run commands, scripts, or programs without leaving the coding environment. For example, you can compile code, run a development server, install dependencies, or manage files. It's very helpful for developers because it allows you to code and execute commands in one place, streamlining your workflow.

```{figure} figures/VSCterminal.*
---
name: fig_VSCterminal
width: 100%
---
The VSC terminal to interact with the computer using the command line
```

### Extensions
Extensions in Visual Studio Code (VSC) are powerful add-ons that enhance the functionality of the editor by providing additional features, tools, and support for various programming languages, frameworks, and technologies. Extensions allow you to customize and tailor VSC to suit your specific development needs.

#### How to Install Extensions:
- Access Extensions View:
    * Click on the Extensions icon in the Activity Bar on the side (or press Ctrl+Shift+X / Cmd+Shift+X).

- Search for Extensions:
    * In the Extensions view, you can search for the name or keywords related to the extension you want to install.

- Install the Extension:
    * Click the Install button on the desired extension, and it will automatically be added to VSC.

- Manage Installed Extensions:
    * You can view, enable, disable, or uninstall extensions from the same Extensions view.

#### Popular Extensions in VSC:
* Python: Provides linting, debugging, IntelliSense, and more for Python development.
* Jupyter: Provides support for Jupyter notebooks within VSC.
* Arduino: Provides support for programming in Arduino.
* Code Spell Checker: Has a great spelling checker, also available for Dutch
* Github Copilot: Your AI pair programmer. Helps you in writing code.
* LaTeX workshop: LaTeX coding, preview, compiling.
* MyST-Markdown: The official Markdown syntax extension


## MystMD




### Requirements.txt
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



## Jupyter lab

We can make use of .ipynb files which are Jupyter Notebooks. To run these notebooks we can use IDE’s as Jupyter Notebook or Jupyter Lab. Jupyter Notebook is a web-based interface that allows users to create and share documents with live code, visualizations, and narrative text in a linear format. JupyterLab, on the other hand, is a more advanced interface offering a flexible and modular environment with multiple panels, including notebooks, terminals, and text editors, providing a more versatile experience for interactive computing. I prefer to use Jupyter lab.


## Typst
For this template we use Typst to produce a high quality pdf. If you want to create pdf's locally, you'll have to install Typst. Follow the [Typst installation instructions](https://github.com/typst/typst?tab=readme-ov-file#installation) for several options to install Typst. We strongly recommend using the latest releases of Typst. If you get a confusing Typst error, a good first step is to upgrade your version of Typst.
