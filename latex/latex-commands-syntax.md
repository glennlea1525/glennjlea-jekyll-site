---
layout: article
title: LaTeX commands overview
type: latex
excerpt: Here is a (very) brief overview of LaTeX commands.
date: '2020-04-30'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc} 

The following sections provide an overview of LaTeX syntax.

**Note:** File extensions are not necessary in a LaTeX file. For example, `mystyles.sty` is the same as `mystyles` to the LaTeX typesetter.

## LaTeX commands begin with a backslash

A backslash lets the LaTeX typesetter know that a particular line is a command.

For example `\documentclass`, `\begin`, `\include` and are all LaTeX commands. They let the LaTeX typesetter know how to handle the information within brackets, curly brackets or default values.

The following shows commands within a LaTeX file. Command arguments are included within curly brackets, while command options, if any, are included within square brackets preceding the argument.

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

## Setting fonts for the document

Another example of a command are font settings. The following changes the font style of the text within the curly brackets to emphasis:

```latex
\emph{This text emphasized}
```

LaTeX has hundreds of commands. Don't worry though. Most of them you wont use. In these topics, we only focus on the most important commands, as I see it, needed to produce technical documentation.

## Command arguments are included within curly brackets

Command arguments are included within curly brackets { }. Here are the first two commands from the example above.

```latex
\documentclass[a4paper,12pt,draft,twoside]{book}
\usepackage{styles/mystyles}
```

The command `\documentclass` provides the argument `{Book}` to tell the LaTeX typesetter to use the `{book}` package for the document layout. The information within the square brackets are the command options that you give to the LaTeX typesetting to define how to use the argument.

Similarly, The command `\usepackage` provides a path to a styles file called `{mystyles}`.

## Commands can act as on-off switches

You can tell the LaTeX typesetter to set a command without a scope. When the LaTeX typesetter encounters a command that does not have a scope, it will set all text that follows the command according to the command. The following is a command without an argument.

`\large`

This command will make all text that follows the `/large` command to the font size according to the switch. When the LaTeX typesetter encounters a different switch, then the font size will change.

## Commands can include options

Options are provided within square brackets [ ] immediately after the command name but before the command arguments.

`\documentclass[a4paper,12pt,draft,twoside]{book}`

The `\documentclass` using the `book` argument includes a set of options are provided to the LaTeX typesetter to indicate the paper size, base font size, document status, and pagination.

## Redefine commands using renewcommand

The `\renewcommand{}` redefines a command. For example, these two commands changes the default LaTeX settings for rule widths to 0 which essentially removes them from the document.

  ```latex
\renewcommand{\headrulewidth}{0pt}
\renewcommand{\footrulewidth}{0pt}
```

## Using reserved characters

LaTeX has 10 special (reserved) characters that are used in LATEX commands:

`\ # $ % &amp; ~ _ ^ { }`

To insert a backslash:

`\textbackslash`

To insert a tilde:

`\textasciitilde`

To insert a caret:

`\textasciicircum`

Other special characters are entered as text by preceding them with a backslash.

## Commenting out lines

You can use several methods to comment out lines in LaTex. Use either `%` or `\comment` and `\endcomment` commands. However, the `\comment` commands require the `Comments` package.

`% Commented out text`

```latex
\Comment
Lots of text that goes on and on that 
needs to be commented out.
\endcomment
```

## Using text and line spacing

Extra spacing between words and commands is ignored.

```latex
\Large   This   is   a   sample   text   with   extra   spacing.
```

Blank lines indicate a new paragraph.

This is an amazing sentence containing consonants and vowels, as well as containing nouns and verbs.

This is yet another amazing sentence that somehow missed an ending point and therefore is a bad example of a sentence

## Adding comments to LaTeX files

Comments are added using the % character. Any text or commands following the % character are ignored.

```latex
% First Include
\include{tex/preface}
% Second Include
\include{tex/intro}
% Third Include
\include{tex/chap01}
% Fourth Include
\include{tex/chap02}
% Fifth Include
\include{tex/summary}
```

## Environment commands

LaTeX has a number of environment commands that are required by the LaTeX typesetter to know how to handle the lines following the command. These include document environments and list environments.

### Document environments

Environments define structures in LaTeX. For instance, the environment variable `\begin` with the argument `{document}` tells the LaTeX typesetter that the document begins at this point and ends at the `\end` command.

```latex
\documentclass[a4paper,12pt,draft,twoside]{book}
\usepackage{styles/mystyles}

\begin{document}
\frontmatter
\tableofcontents
\mainmatter
\backmatter
\end{document}
```

### List environments

Other environment commands include both ordered and unordered lists. For example:

```latex
\begin{itemize}
   \item
   \item
   \item
\end{itemize}
```

### Auto-numbered environments (sections and equations)

Some environments are automatically numbered such as sections and equations. Auto-numbering can be switched off using an asterisk (*). For example:

```latex
\begin{equation*}
\end{equation*}
```

[Next: LaTeX project file structure](/latex/latex-project_file_structure.html)
