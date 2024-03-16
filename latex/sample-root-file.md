---
layout: article
title: Sample root file
type: latex
excerpt: Here is a sample root file that you can use right away to get you started.
date: '2020-04-30'
section: latex
categories:
  - latex
---

# {{ page.title }}

Here is a sample root file that you can use right away to get you started. It is typically named `main.tex` and saved to the root of the project.

```latex
% Manual ROOT FILE
% Copyright 2020 Glenn J. Lea

%\RequirePackage[l2tabu, orthodox]{nag}

\documentclass[a4paper,11pt,twoside]{book}
\usepackage(makeidx)
\usepackage{styles/template}

\begin{document}

\frontmatter
% Configuration of the header strings for the frontmatter pages.
\setcounter{tocdepth}{3}
\fancyhead[RE,LO]{}

% Document Title Page
\input{MANUAL/manual-titlepage.tex}
%\thispagestyle{empty}
\newpage
\pagecolor{white}

% Forward Section  
% \section*{Foreward}
\textbf{Document Information}

%% Document information table
\begin{center}
\begin{longtable}{&gt;{\RaggedLeft}p{4cm}|&gt;{\RaggedRight}p{10cm}}
  \endfirsthead \multicolumn{2}{l}{\textit{Document Information continued}}\
  \endhead \multicolumn{2}{r}{\textit{Continued on next page}}\
  \endfoot
  \endlastfoot
  \textbf{Item} &amp; \textbf{Description}
  Document Version &amp; Version #\\
  Revision Number &amp; Rev #\\
  Document ID #\
  Date Published #\
\end{longtable}
\end{center}

% Copyright Information
\textbf{Copyright Information}
\textbf{Glenn J.Lea}\\
\textbf{Additional Information}\
\newpage

%% Table of Contents
\tableofcontents
\newpage

%% List of tables
\listoftables
\newpage

%% List of Figures
\listoffigures
\newpage 

%% Main part of the document
\mainmatter{}

%% Configuration of the header strings for the main pages.
%%\fancyhead[RE,LO]{\thesection}
\fancyhead[RO,LE]{\bfseries\leftmark}
\fancyhead[RE,LO]{\bfseries\rightmark}

%% Input all external files of the document
%% You must use the \input(filename.tex) form  
\input{MANUAL/manual-ch01-preface.tex}
\input{MANUAL/manual-ch02-overvew.tex}
\input{MANUAL/manual-ch03.tex}
\input{MANUAL/manual-ch04.tex}
\input{MANUAL/manual-ch05.tex}

%% Appendix Inputs
\appendix
\input{MANUAL/app01.tex}
\input{MANUAL/app02.tex}
\input{MANUAL/app05-glossary.tex}

\backmatter
\end{document}

```

[Next: Selecting the Document Class](/latex/documentclass.html)
