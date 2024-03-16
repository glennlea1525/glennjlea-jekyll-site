---
layout: article
title: Defining page size, margins and layout
type: latex
excerpt: You use packages and settings to define the page size, margins and layout.
date: '2020-04-22'
section: latex
categories: latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

You use several packages and settings in the project stylesheet to define the page size, margins and layout of the document. This topic goes through each of the settings to give you an idea of how this is done. 

This should be done before customizing headers and footers,

## Setting the page size

Page size is defined when the LaTex document class, in this case `book`. In this example, the page size is defined as A4 which in the stylesheet is set as mm values: 210mm x 295mm. Alternately, you can use `letterpaper` for US letter size. Using the `book` class, this command sets the page size to A4, the base font size to 11pt and pagination to double-sided.


```latex
\documentclass[a4paper,11pt,twoside]{book}
```


## Using the geometry package

The `geometry` package defines page dimensions. It provides many arguments but I only used the following two arguments:

- `vcentering` which sets vertical auto-centering
- `dvips` which writes the paper size in the dvi output

  The `dvips` option is superceded if `pdflatex` is used but is necessary to generate a correct PostScript bounding box under standard LaTeX.

The `\geometry` command sets the `papersize` precisely, where

- `papersize` determines the size of the paper, which in this case is 210mm by 295mm.
- `total` defines the bounding box for the content area of the document. It is 160mm x 185mm, which results in pleasing margins.

You then add this to the preamble in your stylesheet.

```
\usepackage[vcentering,dvips]{geometry}
\geometry{papersize={210mm,295mm},total={160mm,185mm}}
```


## Defining offsets for headers and footers

You need to allow space for the headers and footer on the page. This can be done using the package `geometry` to define the offsets for headers and footers between the body text and the footers. 

For example, use the following commands for an A4 page size.

```
\setlength\voffset{-1in}
\setlength\hoffset{-1in}
\setlength\topmargin{1cm}
\setlength\oddsidemargin{3cm}
\setlength{\evensidemargin}{3cm}
```


## Defining text flow size

The height of the text flow on each page is defined using `textheight`. The original setting for text height was 24.5. The following command changes it to 23.5cm.

```
\setlength\textheight{23.5cm}
```

The width of the text flow is defined using `textwidth`. The original setting for text height was 16cm. The following changes it to 15cm.

```latex
\setlength\textwidth{15cm}
```

## Defining the distance between text flow and headers and footers

The command `footskip` defines the distance between the footer and the text flow.

```latex
\setlength\footskip{1.0cm}
```

The commands `headheight` and `headsep` define the distance between the header and the text flow.

```latex
\setlength\headheight{1cm}
\setlength\headsep{1cm}
```

## Paragraph settings

You can indent the first line of paragraphs using the `paarindent` command. If you set the indentation to 0cm then the paragraphs do not have an indentation.

```latex
\setlength{\parindent}{0cm}
```

You can set the spacing between paragraphs in points using `\parskip`. In the following example, the distance is set to 3 pts.

```latex
\setlength{\parskip}{3pt}
```

Line spacing is determined by these commands. In the following example, line spacing is set to 1.5 using the `\setspace` package. Options are commented out.

```latex
\usepackage{setspace}
\singlespacing
%\onehalfspacing
%\doublespacing
\setstretch{1.1}
```

Alternately, you can use the command `\baselinestretch` but you can adjust the command using `\renewcommand`.

```latex
\renewcommand{\baselinestretch}{1.5}
```

[Next: Customizing headers and footers](/latex/customizing-headers-footers.html)
