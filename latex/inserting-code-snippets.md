---
layout: article
title: Inserting code snippets
type: latex
excerpt: Here is some syntax you can use to insert code snippets and code highlighting in a text flow.
date: '2020-04-30'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

## Selecting a package

The `verbatim` and `listings` packages can be used for inserting in a text flow source code snippets and code highlighting. However, I found the Listing package`lstset` best suited my needs for technical documentation. from the Listing package documentation:

> The `listings` package is a source code printer for LATEX. You can typeset stand alone files as well as listings with an environment similar to verbatim as well as you can print code snippets using a command similar to `\verb`. Many parameters control the output and if your preferred programming language isn’t already supported, you can make your own definition.

These packages are inserted using the following commands:

```latex
\usepackage{listings}
\usepackage{verbatim}
```

## Inserting code in a specific environment

You can put code inside a corresponding environment. For example, for SQL commands, you could use the following.

```latex
\begin(codesql)
SQL Command syntax, etc.
\end(codesql)
```

Other environments include:

- codesh - shell commands
- codecsv - CSV commands
- codecpp - C++
- codejava - Java code
- codejson JSON
- codexml - XML

## Using the verbatim package to insert code

LaTeX provides a default command `verbatim` for inserting code. It ignores all text and commands within the environment and outputs the text in monospaced font.

```latex
\begin{verbatim}
  /* HelloWorld.java
  */
   public class HelloWorld
   {
     public static void main(String[] args) {System.out.println("Hello World!");}
   }
\end{verbatim}
```

## Using the listings package

The `listings` package supports most common languages. To include this package, add the following line to the stylesheet.

`\usepackage{listings}`

First, define the colours for the source code:

\definecolor{dkgreen}{rgb}{0,0.6,0}
\definecolor{gray}{rgb}{0.5,0.5,0.5}
\definecolor{mauve}{rgb}{0.58,0,0.82}
\definecolor{lightgrey}{RGB}{211,211,211}

Then configure the listing using `\lstset`:

```latex
\lstset{
  frame=tlrb,
  frameround=tttt,
  framerule=0.2pt,
  rulecolor=\color{lightgrey},
  language=SQL,
  aboveskip=3mm,
  belowskip=3mm,
  showstringspaces=false,
  columns=flexible,
  basicstyle={\small\ttfamily},
  numbers=none,
  numberstyle=\tiny\color{gray},
  keywordstyle=\color{blue},
  commentstyle=\color{dkgreen},
  stringstyle=\color{mauve},
  breaklines=true,
  breakatwhitespace=true tabsize=3
}

\lstset{language=SQL}

\newcommand{\inlineCode}{\lstinline[basicstyle=\normalsize\ttfamily]}
```

Then add your code sample, changing the language setting accordingly:

```latex
\begin{lstlisting}[language=java]
    /* HelloWorld.java
    */

    public class HelloWorld
    {
        public static void main(String[] args) {
        System.out.println("Hello World!");
       }
    }
\end{lstlisting}
```

[Next: Creating custom title pages](/latex/creating-custom-title-page.html)
