---
layout: article
title: Numbering
type: latex
excerpt: Create numbering when the list is interrupted by a paragraph.
date: '2020-04-30'
section: latex
categories:
  - latex
---
# {{ page.title }}

Creating ordered lists is relatively easy in LaTex. Two packages are available. You can use either the `enumitem` or `mdwlist` packages for numbering.

## Using the enumitem package

Numbering is defined using the `enumitem` package. Using a `resume` command, you can continue the numbering after a break due to a paragraph. 

For example, you define the package for the document using `enumitem`.

```latex
\usepackage{enumitem}
```

Then in the document you insert the list using `enumerate` as follows. 

```latex
\begin{enumerate}
  \item List item
  \item Another list item
\end{enumerate}
```

Suppose you have an indented paragraph and you want to resume the list after the paragraph, you would insert the following.

```latex
\begin{enumerate}
  \item Further item
  \item Final item
\end{enumerate}
```

## Using the mdwlist package

You can also use `mdwlist` package (which is part of `mdwtools`).

You define the `mdwlist` package as follows:

```latex
\usepackage{mdwlist}
```

Then in the document you insert the list using `mdwlist` as follows:

```latex
\begin{enumerate}
\item List item
\item Another list item
\suspend{enumerate}
```

Then you can insert a paragraph for the second list item, then continue to list as follows:

```latex
\resume{enumerate}
\item Further item
\item Final item
\end{enumerate}
\end{document}
```

[Next: Creating LaTeX Stylesheets](/latex/latex-stylesheets.html)
