---
numbering:
  title:
    offset: 1
---

# Plugins 🌶

Plugins allow you to extend the functionality of Jupyter Book. 
In this workshop-template, we make use of a single plugin:

:::{literalinclude} ../../myst.yml
:start-at: plugins:
:end-before: # exports and downloads
:lineno-match:
:caption: We make use of plugins in this workshop-template.
:label: less2_code_plugins
:::

This plugin allows you to create a custom admonition:

```{experiment} Let's do a fun physics experiment!
Have two coins A and B touching and a third coin (C) lengthwise at a few cm distance.
Then shoot coin C towards B while pressing B down with your finger.
If coin A and coin B touch, then the momentum transfers very well to coin A even though B is not able to move.
The transmission mechanism inside coin B must be a wave.
Coin A can also be put such that it is not quite in line with coin B but still touching B.
Also then momentum transfer takes place and A is launched under an angle.
```

```{tip} 
Plugins are shared in a [GitHub repo](https://github.com/jupyter-book/myst-plugins/)
```

```{exercise} Include a plugin
Look at the different plugins available in the [myst-plugins GitHub repo](https://github.com/jupyter-book/myst-plugins/). 
Include one of them in your own `myst.yml` file and use it in a page of your book.
Rebuild the book and look at your changes.
```