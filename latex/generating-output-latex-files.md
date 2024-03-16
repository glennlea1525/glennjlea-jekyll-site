---
layout: article
title: Generating output from a LaTeX project
type: latex
excerpt: After creating a LaTeX file, It needs to be built using the TeX distribution to generate an output PDF file.
date: '2020-04-24'
section: latex
categories:
  - latex
---
# {{ page.title }}


* Do not remove this line (it will not be displayed)
{:toc}

After creating a LaTeX file, it needs to be built using the TeX distribution to generate an output PDF file. Lets look at how to generate an example output file from a LaTeX `.tex` file.

## Example HelloWorld.tex file

Here is an example Hello World file. You can type the following in a LaTeX editor and save the file as `HelloWorld.tex`.

```latex
\documentclass{article}
\begin{document}
\title{Title of Document}
\author{Your Name}
\date{\today}
\maketitle
\tableofcontents
\section{Section Head}
  Hello, world!
\section{Second Section Head}
  This is the last thing I am going to say here!
\end{document}
```

## Build the file

Next, build the file on the command line or in a LaTeX editor such as TeXworks. See <a href="/latex/1-2-installing_distributions">Selecting a LaTeX distribution and editor</a> for more information.

In TeXworks, for example, select the build option *pdfLaTeX+MakeIndex+BibTex* from the *Build* menu, then click *Build* (the arrow next to the dropdown menu).

Alternately, open a terminal (MAC) or Command Prompt (Windows) and change to the directory where you saved the file. Then run the following command **twice** to build the file and to generate a table of contents:

```latex
pdflatex HelloWorld.tex
pdflatex HelloWorld.tex
```

## Completed build saved in root directory

In the directory containing `HelloWorld.tex` you will find a whole bunch of new files in there. Find the file `HelloWorld.pdf` and open it in a pdf viewer. You should see the following output.

<p><img class="img" src="{{ baseurl }}/assets/img/latex/hello-world.png" alt="LaTeX document with table of contents" ></p>
<p class="center">LaTeX document with table of contents</p>

[Return to start](../latex.html)
