---
layout: article
title: Formatting chapter sections
type: latex
excerpt: Chapters in LaTeX require specific commands and use section headings which are pulled out into the Table of Contents.
date: '2020-04-29'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}


## A note about file structure

If a document consists of multiple chapters, then it is good practice to create one `.tex` filer per chapter. For example:

- `chapterone.tex`
- `chaptertwo.tex`
- `chapterthree.tex`
- `chapterfour.tex`

Then you define the title and other information at the top of each chapter using specific commands. Furthermore, the document's TOC (Table of Contents) are built using the chapter title and each chapter's section headings. You can also add index entries for the chapter.

## Defining a chapter title

Each chapter begins with the following elements:

```latex
\chapter{Overview}  % Chapter title
\label{sec:Overview} % Used for cross-referencing
\index{overview} % Used for indexing
```

- The first line requires you to define the title of the chapter. This is used in the headers and in the Table of Contents.

- The second line is used for cross-referencing to this chapter. It serves as a marker or anchor.

- The third line is used by the index.

For example:

```latex
\typeout{}
\typeout{=====================================================================}
\typeout{==== Installing Software}
\typeout{====}
\typeout{==== installing.tex}
\typeout{=====================================================================}
\typeout{}
% The above lines are printed out in a terminal to indicate this file is being processed.


\chapter{Installing Software}
\label{sec:Preparing to Install Software}
```

## Section headings

Creating a section headings is quite easy - use the `section` command. Second and third level headings are just as easy. These levels use `subsection` and `subsubsection` commands. For example:

```latex
\section{heading text}
\subsection{heading text}
\subsubsection{heading text}
```

Note: Three levels of headings are best. Any more and you may need to rewrite sections so they are at most third level deep. If you must, then just use a bolded paragraph for a fourth level heading.

## Paragraphs

Paragraphs are entered without markup tags. Adding a new paragraph simply requires a blank line between paragraphs.

```latex
This is the first paragraph about Road Runners.

This is the second paragraph about Road Runners.
```

## Comments

You can add comments to a `.tex` file as required using the `%` character.

```latex
% Add a comment using this character and LaTeX will ignore the rest of the current line.
```

## Paragraph line breaks

You can add a line break into text by adding a backslash {\\} or using the `\newline` command. However, these two commands are not entirely identical. The backslash provides two optional parameters.

The following command tells LaTeX to start a new line. 

`\`

The following command tells LaTeX not to start a new page after the line by issuing a `\nobreak`.

`\*`

The following command specifies the vertical space `<len>` to be inserted before the next line. This value can also be negative.

`\[<len>]`

Note: The above two can also be mixed. That is, using both a starred + optional argument combination `\*[<len>]`.

The following command is similar to the backslash.

`\newline`

## Indenting paragraphs in lists

You can define the indentation value of paragraphs within lists in the stylesheet then apply the command where needed.

```latex
\newenvironment{myindentpar}\[1\]\[1\]%
{\begin{list}{}%
  {\setlength{\leftmargin}{#1}}% \item[]% }
  {\end{list}}
```

Then Use `myindentpar` in the document flow to indent a paragraph based on the settings.

`\begin{myindentpar}{1cm} % text text text... % \end{myindentpar}`

Note that you can adjust the indent in this command as required.

[Next: Commands for font formatting and lists](/latex/formatting-text.html)
