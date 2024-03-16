---
layout: article
title: Creating custom tables
type: latex
excerpt: You can add simple to complex tables to a LaTeX document using several types of packages, depending on the requirements of the table.
date: '2020-04-24'
section: latex
categories:
  - latex
---

# {{ page.title }}


* Do not remove this line (it will not be displayed)
{:toc}

You can add simple to complex tables to a LaTeX document using several types of packages, depending on the requirements of the table.

## Inserting table packages

LaTeX provides several packages for adding tables to a LaTeX document. Two useful packages for tables are the `tabular` and the `supertabular` package. 

Note: When using `tabular` or `supertabular`, the cell contents are in text mode.

## Defining a table using the tabular package

Using the `tabular` package you can, for example, define a basic table with a header, three columns and rows as follows:

```latex
\begin{center}
\begin{tabular}{|l|l|l|}
Column Heading & Column Heading & Column Heading \\\
\hline
Cell contents & Cell contents & Cell contents \\
Cell contents & Cell contents & Cell contents \\
Cell contents & Cell contents & Cell contents \\
\end{tabular}
\end{center}
```

This explains what is happening in this definition:

- The line `\begin{tabular}{|l|l|l|}` creates a table with three columns that are left aligned and have a vertical line between each column.

- Next, column headings are added where each heading is marked off by a `&` symbol and where the row is ended with the command `\\`.

- A horizontal line is added using `\hline`.

The cell contents follow the same structure as column headings.

## Defining a more complex table using supertabular

Using `supertabular` you can create more complex tables by adding the following commands to the stylesheet:

```latex
\usepackage{supertabular}
\usepackage{xcolor}
\usepackage{tikz}
\usepackage{longtable}
\usepackage{tabulary}
\usepackage{colortbl}
```

Then you can create a table as shown in the following example:

```
\begin{flushleft}
\tablehead{}
\begin{supertabular}{|m{2cm}|m{6cm}|}
\hline
Heading 1 & Heading 2\\\hline
1st column and 1st row & 2nd column and 1st Row\\\hline
1st column and 2nd row & 2nd column and 2nd Row\\\hline
1st column and 3rd row & 2nd column and 3rd Row\\\hline
1st column and 4th row & 2nd column and 4th Row\\\hline
\end{supertabular}
\end{flushleft}
```

This explains what is happening in this definition:

- The environment command `\begin{flushleft}`places the table left aligned to the margin. 

- The command `\tablehead{}` adds a table heading. In this case, it is empty so no table heading is used.

## Adding spacing to table cells

You can add spacing above and below the text in table row as follows:

```latex
\setlength{\extrarowheight}{4pt}
```

Here is an example of it used in a table.

```latex
\begin{footnotesize}
\setlength{\extrarowheight}{7.6pt}
\begin{tabular}{l|m{7cm}}
\hline
\hline
Cell contents & Cell contents  \\\hline
\hline
Cell contents & Cell contents  \\\hline
Cell contents & Cell contents  \\\hline
Cell contents & Cell contents  \\\hline
\hline
\end{tabular}
\end{footnotesize}
```

[Next: Formatting chapter sections](/latex/formatting-chapter-sections.html)
