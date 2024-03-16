---
layout: article
title: LaTeX Project file structure
type: latex
excerpt: Here is a suggested structure for your LaTeX project.
date: '2020-04-30'
section: latex
categories:
  - latex
---
# {{ page.title }}


* Do not remove this line (it will not be displayed)
{:toc}

You can organize your project structure any way you want, of course. The suggested structure described in this topic allows me to keep the organization of the project manageable.

## LaTeX Projects

A LaTeX project consists of a set of files having a .tex extension, as well as image files and stylesheets having a .sty extension.

A User Guide or Reference Manual should, ideally, be created from multiple files, usually one file per chapter and a single root file that you would use to generate the output.

A root file is the main LaTeX file that the LaTeX typesetter uses to collect the style sheets, title page, chapters and appendices, and generate output using the defined headers and footers, TOC and so forth. Typically, you want to name it something like `main.tex` or similar.

When creating a project file structure, a root file is placed in the root of the directory. All chapter .tex files, image files and stylesheets are placed in sub-directories. This allows for better file management.

To build the LaTeX document, you then need only run the build command on the root file to generate output.

## Suggested project file structure

The following shows the suggested structure of a documentation project directory.

```latex
Root
├── main. tex                              # main root file
├── \styles\stylesheet.sty                 # project stylesheet
├── \content (or tex)                      # .tex topic (chapter) files
├── \img                                   # image files
├── \titlepage                             # document title layout
├── \common                                # common files
```

[Next: LaTeX main file](/latex/latex-main-file.html)
