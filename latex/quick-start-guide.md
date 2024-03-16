---
layout: article
title: LaTeX quickstart
type: latex
excerpt: Use this Quick Start to build a sample document
date: '2020-04-30'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}


LaTeX can be used to develop very good technical documentation, but it requires the use of specific document classes, packages and settings.

What follows in this and upcoming topics is entirely my own experience having to create high quality user guides and manuals using LaTeX. Much of it was trial and error until I finally landed on a good set of tools to do the job. Consultants, clients and Stack Overflow helped considerably.

So, to get you up and running quickly, here is the most basic of LaTeX projects - an *Article*. The  simple steps that follow will guide you through generating a pdf file from a sample LaTeX file.

----------------------- ------------------------------------
**Note:** If you have some experience with LaTeX you can skip this topic and jump right in using the more details topics that follow this topic.

----------------------------------------------------------------

## Install the Distributions

You first need to install a TeX distribution such as ProTeXt and MacTeX. You will also need an editor such as TeXnicCenter, TeXworks or Eclipse. Atom probably works just as well.

For this Quick Start, we will use the MikTex distribution and TeXworks editor. For MikTex, see [miktex.org](https://miktex.org/). For TeXworks, see [github.com/TeXworks/texworks/releases](https://github.com/TeXworks/texworks/releases) They are relatively easy to install and set up. MikTex will install the base program and, if you make the selection, automatically install missing packages. TeXworks allows you to easily compile to PDF the documents.

So, select a distribution and choose a good LaTeX editor:
- Notepad++
- Texmaker
- Texnicle

----------------------- ------------------------------------
**Note:** For information about TeX distributions and LaTeX editors, see
[
Installing LaTeX distributions](../pages/latex/1-4-installing_distributions/index.md)

----------------------------------------------------------------

## Create a Sample Document

Open a LaTeX editor such as TeXworks and enter in the following exactly as shown.

```latex
\usepackage{palatino,url}
\documentclass[12pt]{article}
\begin{document}
\section*{My first document}
This is a short example of a \LaTeX\ document written
\today. It shows a few simple features of automated
typesetting, including
\begin{itemize}
\item setting the default font size to 12pt
\item specifying an article type for formatting
\item using the Palatino typeface
\item adding special formatting for URIs
\item formatting a heading in section style
\item using the \LaTeX\ logo
\item generating today's date
\item formatting a list of items
\item centering and italicizing
\item autonumbering the pages
\end{itemize}
\subsection*{More information}
This example was taken from Formatting Information,
which you can download from
\url{http://www.ctan.org/tex-archive/info/beginlatex/}
and use as a teach-yourself guide.
\begin{center}
\textit{Some text to close the document}
\end{center}
\end{document}
```

Here is the document in Texworks.

<img class="img" src="{{ baseurl }}/assets/img/latex/qs-texworks.png" alt="Quick Start document" >
<p class="center">Quick Start document in Texworks.</p>

## Save the file

After entering the text, create a directory called `/sampleLatex`. Save the file you just created in that directory and call it `QuickStart.tex`.

## Compile (build) the LaTeX File

The file needs to be built (or compiled) to generate a PDF file. The preferred way is to use a LaTeX editor such as TeXworks or TeXnicCenter.

In TeXworks, do the following:

1. Select the build option *pdfLaTeX* from the *Build* menu, then click *Build* (the arrow next to the dropdown menu).
2. The resultant pdf file is in the root of your project.

Here is the output of the LaTeX file as PDF.

<img class="img" src="{{ baseurl }}/assets/img/latex/qs-pdf-out.png" alt="Quick Start document PDF output" >
<p class="center">Quick Start document PDF output.</p>

----------------------- ------------------------------------
**Note:** You could also use the command line if you have MikTex in your path. To build the LaTeX file using the command line. Follow the instructions in MikTex.

----------------------------------------------------------------

[Next: Sample LaTeX file - Hello World](/latex/sample-latex-file.html)
