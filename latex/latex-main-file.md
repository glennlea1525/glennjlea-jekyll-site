---
layout: article
title: LaTeX root file - main.tex
type: latex
excerpt: A LaTeX root file main.tex tells the LaTeX typesetting how to build the document.
date: '2020-04-30'
section: latex
categories:
  - latex
---
# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

A LaTeX root file main.tex tells the LaTeX typesetting how to build the document. The title page, stylesheets, table of contents, chapters, and appendices are references in the root file using `\include` commands.

## Simplified root file

The following is a simplified root file.

```latex
\documentclass[a4paper,12pt,draft,twoside]{book}
\usepackage{styles/mystyles}

\begin{document}
\frontmatter
\include{tex/title}
\tableofcontents
\mainmatter
\include{tex/preface}
\include{tex/intro}
\include{tex/chap01}
\include{tex/chap02}
\include{tex/summary}
\backmatter
\end{document}
```

Let's go through this file line by line.

**Note:** Commands included before the `\begin{document}` command apply to the entire document. They are outside any scope, or fixed section of the document stream.

## Define the document class

The first line tells the LaTeX generator the type of document it is about to generate (or typeset) and what styles are to be used.

```
\documentclass[a4paper,12pt,draft,twoside]{book}
```

All these elements are defined in separate class files (more about these classes later).

`\documentclass` tells the LaTeX generator the type of document you intend to create. This document will be printed (or output to pdf) in A4 format. The base font will be 12 points, although this can be modified in the document. It is marked as draft initially. And it will be printed on both sides.

`{book}` tells the typesetter to use the `book` class. This is a set of predefined outputting instructions, which in this case has functionality that can handle large multi-chapter documents.

## Reference the stylesheet

The next line tell the typesetter to use the styles defined in an external document called `mystyles` located in the `styles` directory.

```latex
\usepackage{styles/mystyles}
```

`mystyles` is the name of the stylesheet where all the styles have been defined that will be used in this document. This allows you to update the stylesheet without having to worry about finding the styles within the root file (which is the alternate location for styles).

## Begin the document scope

Like the `<body>` tag in HTML, the actual content follows this tag. The `\begin` tag tells the typesetter that what follows is the document.

```latex
\begin{document}
```

You put meta information and additional instructions before this tag such as `\title`, `\author`, `\date`, and so on.

The document section is divided into three sections:

`\frontmatter`
`\mainmatter`
`\backmatter`

## Insert the title page and table of contents

Within the `\frontmatter`section, you include a title page. Alternatively, the `{book}` class has a default title page which can be referred to simply as `titlepage`.

Also, in this section you can add a table of contents, which is then automatically generated during output.

```latex
\frontmatter
\include{tex/title}
\tableofcontents
```

## Insert the document content

The document itself - the contents - is contained within the `\mainmatter` section.

```latex
\mainmatter
```
You then follow this tag with references to the topics, or chapters, of the document.

**Note:** To keep this simple and to allow chapters to be toggled off or on (included/excluded) as required, my practice is to place topic contents in sets of files contained within a subdirectory called `\tex`.

The `\include` command tells the typesetter to include the file referenced within the curly braces in the output stream at the location in the list of includes. You can easily rearrange the topics by rearranging these `\include` lines in this list.

```latex
\include{tex/preface}
\include{tex/intro}
\include{tex/chap01}
\include{tex/chap02}
\include{tex/summary}
\include(tex/appendix)
```

## Insert an index, if required

A `\backmatter` section can also be included, which typically includes the Index.

```latex
\backmatter
```

**Note:** You would also define your headers and footers here, but I excluded them in this example to keep it simple. I will get to them in due time.

## End the Document Scope

You need to tell the typesetter when the document is complete and that there are no more files to generate. In other words, you need to close your document, as with html `</html>`.`

```latex
\end{document}
```

This simple command indicates the end of the document. Now, we can go ahead and generate the output.

[Next: Sample root file](/latex/sample-root-file.html)
