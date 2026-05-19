# getting-started-quarto-asa-cirs

Materials for the ASA CIRS Quarto webinar (2026-05-18)

## Setup notes

- R 4.5.2 (2025-10-31) -- "[Not] Part in a Rumble"
- Positron Version: 2026.06.0 build 74
- Quarto 1.10.3
- Packages: tidyverse, palmerpenguins, gt

## Demo

### Documents

- Open the simple Quarto document called `index.qmd` and edit it using the RStudio Visual Editor.
- Bold palmerpenguins and add link to https://allisonhorst.github.io/palmerpenguins/.
- Add code chunk options:
  - `fig-alt`
  - `echo: false` in `execute` in the YAML
  - `code-fold`
  - teaching tip: `echo: fenced`
- Add a figure and a table and cross reference them
- Add a citation: 10.1371/journal.pone.0090081
- Make pdf with `format: pdf`
- Make pdf with `format: typst`

### Slides

- Change `format: revealjs`
- Add section headings: First level headings Introduction and Analysis, under Analysis a second level heading called Modeling
- Add columns to slides
- Reveal code with `echo: true`
  - teaching-tip: `code-line-numbers`
- Change `output-location` of figure

### Websites

- Add another document `about.qmd`
- Add `quarto.yml`

```
project:
  type: website

website:
  title: "Hello Quarto"
  navbar:
    left:
      - index.qmd
      - talk.qmd
```

- Render
- Add other formats to index.qmd:

```
format:
  html: default
  pdf: default
```

- `quarto render`

- Add `_brand.yml`

```
logo: images/logo.png

color:
  palette:
    black: "#1A1A1A"
    white: "#F9F9F9"
    orange: "#FF6F20"
    pink: "#FF3D7F"
  foreground: black
  background: white
  primary: orange
  danger: pink

typography:
  fonts:
    - family: Open Sans
      source: google
    - family: Rubik
      source: google
    - family: IBM Plex Mono
      source: google

  base: Open Sans
  headings:
    family: Rubik
    weight: 400
  monospace: IBM Plex Mono
```

- Update `_quarto.yml` with 

```
brand: _brand.yml
```

- `quarto publish`


### Journal articles

- Go to https://quarto.org/docs/journals/templates.html

- Click on Quarto journals repo

- Create one with JASA template

my-awesome-paper

- Add a citation

First from Zotero
Welcome to the tidyverse

### Teaching

- Add code-link true to the document yaml

format:
  html:
    code-link: true

- Add include = FALSE as a code chunk option and render and review the error, and fix with YAML completion

- Switch to slides

format: revealjs

Don't need to change anything else 

- Show the sidebar > Tools for PDF export of slides

- Add chalkboard

format:
  revealjs:
    chalkboard: true

- Add multiplex

format:
  revealjs:
    chalkboard: true
    multiplex: true

Show the files generated and which to post

- Add execute: true to document yaml

execute: 
  echo: true

- Show echo: fenced for a code chunk

- Convert to document - Code annotation (1.3 PRERELEASE)

  to scale_color_colorblind() # <1>
  to theme elements           # <2>

  1. Use a color-blind friendly color scale
  2. Adjust theme elements
