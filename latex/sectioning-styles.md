---
layout: article
title: Defining sectioning styles
type: latex
excerpt: Two packages titlesec and sectsty are used to set sectioning styles.
date: '2020-04-30'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

A section in a document usually consists of a chapter title as well as first, second and third level headings. The `titlesec` package is used for this and then you define how each of the headings are formatted. 

Note: For some of the long commands, I added line breaks for readability. You need to remove those breaks when using the syntax.

## Using the titlesec package

To set sectioning styles and packages, you can use the `titlesec` package. `titlesec` pro­vid­es an in­ter­face for defining var­i­ous ti­tle styles.

```latex
\usepackage{titlesec}
```

## Defining chapter titles

I configured the chapter title to have a 19pt font size.

```latex
\titleformat{\chapter}{\fontsize{19pt}{0em}\selectfont\bf}{\thechapter.}{1em}{}
```

To remove the large space above the chapter title:

```latex
\titlespacing*{\chapter}{0pt}{-30pt}{20pt}
```

To indent the section label:

```latex
\titlelabel{\llap{\makebox[1cm][l]{\thetitle}}\hspace*{25.4mm}}
```

To set the size and position of the chapter heading:

```latex
\titleformat{\chapter}{\fontsize{20pt}{0em}
  \selectfont\bf\color{namecolor}}{\thechapter.}{1em}{}
```

## Defining section headings

To set the size and position of the section headings:

```latex
\titleformat{\section}[hang]
  {\normalfont\Large\bfseries\color{namecolor}}
  {\thesection.}
  {1em}{}

\titlespacing{\section}{0pt}{*4}{*1\.5}
```

For subsection headings:

```latex
\titleformat{\subsection}[hang]
  {\normalfont\Normalsize\bfseries\color{namecolor}}
  {\thesubsection.}{1em}{}
```

For subsubsection headings:

```latex
\titleformat{\subsubsection}[hang]
  {\normalfont\Normalsize\bfseries\color{namecolor}}
  {\thesubsubsection.}{1em}{}
```

[Next: Numbering](/latex/numbering.html)
