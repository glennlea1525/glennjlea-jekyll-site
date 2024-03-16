---
layout: article
title: Footnotes, widows and orphans
type: latex
excerpt: Here are some rules I created for footnotes, widow and orphan control.
date: '2020-04-30'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

Here are a set of commands I created for footnotes, widow and orphan control. You can use them to get started or learn how to make your own set of commands. 

## Footnote rules

This sets the footnote rule which appears just above the first footnote on a page.

```latex
\setlength{\skip\footins}{0.119cm}
\renewcommand\footnoterule{\vspace*{-0.018cm}
\setlength\leftskip{0pt}
\setlength\rightskip{0pt plus 1fil}
\noindent\textcolor{black}{\rule{0.25\columnwidth}{0.018cm}}\vspace*{0.101cm}}
```

## Widow and Orphan Control

You can control widows and orphans using these commands:

```latex
\widowpenalty=300
\clubpenalty=300
```

## Adding Todo notes

You can add this Package to add todo notes in the document as a type of comment. They do not appear in the output but serve as useful reminders for yourself what needs to be done in the section, chapter, whatever.

`\usepackage{todonotes}`

Then insert a note in the doc using the following:

`\todo{Rewrite this answer \ldots}`

At any location in the document a list of the inserted notes can be generated with the following command:

`\listoftodos`

[Next: Defining sectioning styles](/latex/sectioning-styles.html)
