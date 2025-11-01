---
numbering:
  title:
    offset: 0
  start: 5
---

# Styling etc 🌶

## Landing page customization


https://mystmd.org/guide/website-landing-pages


## The cruel difficulty of including correct chapter numbering

## Custom CSS

```{figure} ../figures/css_landingpage.*
:width: 100%
:name: css_landingpage

A JB2 site with custom CSS
```

 

Creating your landing page using CSS
https://mystmd.org/guide/website-navigation#use-the-edit-this-page-button
action button
frontmatter: hide
fronmatter: numbering

+++ {"class": "article"}

<style>
.article h1,
.article h2,
.article h3,
.article h4 {
  font-family: Arial, "Times New Roman", serif;
}

/* ---- Heading colors (light mode) ---- */
.article h1 { color: pink; }   /* slate-900-ish */
.article h2 { color: pink; }   /* blue-700 */
.article h3 { color: red; }   /* sky-500 */
.article h4 { color: green; }   /* slate-500 */
</style>

# Example header
## Subheader
+++


## subfigures side by side
You can enhance your page using tailwind CSS classes. For example, to place two images side by side:

::::{figure}
:class: grid grid-cols-2 items-end gap-4
:label: fig_combined2
:width: 100%

![Banff, Canada](https://github.com/rowanc1/pics/blob/main/banff-wide.png)
![Golden Gate Bridge, San Francisco](https://github.com/rowanc1/pics/blob/main/sfo-wide.png)

Some lovely pictures
::::
