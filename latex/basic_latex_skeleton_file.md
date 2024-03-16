---
layout: article
title: LaTeX skeleton structure
type: latex
excerpt: This is the LaTeX skeleton file that I found on StackExchange that got me started learning how to develop high quality LaTeX based product documentation.
date: '2020-04-30'
section: latex
categories:
  - latex
---
# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

I found this LaTeX skeleton on the TEX StackExchange Site by a user named <a href="https://tex.stackexchange.com/questions/20101/technical-documentation-and-or-book-templates/20110#20110" target="_blank">XPort</a> (opens in new window).

I thought it was quite useful so I reproduced it here to help you get started. It wasn't used in the final product I created but it gave me an idea of how to go about building a LaTeX project for technical documentation.

## Step 1 - Create Project Directories

Divide your project into at least the following subdirectories:

| `MyProject` | Directory containing your LaTeX project files and from which you<br> compile your project.|
| `MyProject\content` | Place all your LaTeX topic files here.|
| `MyProject\img` | Place any topic images here. |
| `MyProject\code` | Place project styles and other non-topic files here.|

## Step 2 - Create your own document class based on book class

Create a document class file to store LaTeX design settings. Name it `mybook.cls` and save it to the root of the `MyProject` directory. Then, add the following content to the file. Descriptions are provided following this file.

```latex
\ProvidesClass{mybook}[2011/06/07 v 0.01 my own class (hv)]
\DeclareOption*{\PassOptionsToClass{\CurrentOption}{book}}
\ProcessOptions\relax
\LoadClass
[
%other default options go  here
]{book}

\newcommand\ContentsPath{Contents/}
\newcommand\ChapterPath{\ContentsPath}
\newcommand\SectionPath{\ChapterPath}
\newcommand\SubSectionPath{\SectionPath}

\@ifclassloaded{book}
{
    \newcommand\IncludeChapter[1]
    {
        \renewcommand\ChapterPath{\ContentsPath#1/}
        \include{\ContentsPath#1}
    }
    \newcommand\IncludeOnlyChapter[1]
    {
        \includeonly{\ContentsPath#1}
    }
}{}
```

```latex
\newcommand\InputSection[1]
{
    \renewcommand\SectionPath{\ChapterPath#1/}
    \input{\ChapterPath#1}
}

\newcommand\InputSubSection[1]
{
    \renewcommand\SubSectionPath{\SectionPath#1/}
    \input{\SectionPath#1}
}

\newcommand\InputSubSubSection[1]
{
    \input{\SubSectionPath#1}
}


\@ifclassloaded{book}
{
    \newcommand\Chapter[1]
    {
        \chapter{#1}
        %\addcontentsline{toc}{chapter}{#1}
    }
}{}

\newcommand\Section[1]
{
    \section{#1}%
    %\addcontentsline{toc}{section}{#1}
}

\newcommand\SubSection[1]
{
    \subsection{#1}
    %\addcontentsline{toc}{subsection}{#1}
}

\newcommand\SubSubSection[1]
{
    \subsubsection{#1}
    %\addcontentsline{toc}{subsubsection}{#1}
}

\RequirePackage{xcolor}

\RequirePackage{listings}
\lstdefinestyle{Common}
{
        breaklines=true,
        tabsize=3,
        showstringspaces=false,
        aboveskip=0pt,
        belowskip=0pt,
        extendedchars=\true,
        language=PHP,
        frame=single,   
        %===========================================================
        framesep=3pt,%expand outward.
        framerule=0.4pt,%expand outward.
        xleftmargin=3.4pt,%make the frame fits in the text area.
        xrightmargin=3.4pt,%make the frame fits in the text area.
        %===========================================================
        rulecolor=\color{Red}%
}

\lstdefinestyle{ThemeA}
{
        style=Common,
        backgroundcolor=\color{Yellow!10},

        basicstyle=\scriptsize\color{Black}\ttfamily,
        keywordstyle=\color{Orange},
        identifierstyle=\color{Cyan},
        stringstyle=\color{Red},
        commentstyle=\color{Green}
}

\newcommand{\IncludeCode}[2][style=ThemeA]
{
    \lstinputlisting[#1,caption={\href{#2}{#2}}]{#2}
}

\RequirePackage[colorlinks=true,bookmarksnumbered=true,bookmarksopen=true]{hyperref}
\RequirePackage[all]{hypcap}

\RequirePackage{makeidx}
\makeindex

\endinput
```

The following sections gives an explanation of the class file.

### Declare a new class mybook based on the book class:

```latex
  \ProvidesClass{mybook}[2020/01/01 my own class (hv)]
  \DeclareOption*{\PassOptionsToClass{\CurrentOption}{book}}
  \ProcessOptions\relax
  \LoadClass [
  %other default options go here
  ]{book}
```

### Define new commands:

```latex
\newcommand\ContentsPath{Contents/}
\newcommand\ChapterPath{\ContentsPath}
\newcommand\SectionPath{\ChapterPath}
\newcommand\SubSectionPath{\SectionPath}
```

### Load the new class:

```latex
\@ifclassloaded{book}
{
  \newcommand\IncludeChapter[1]
  {
    \renewcommand\ChapterPath{\ContentsPath#1/}
    \include{\ContentsPath#1}
  }
  \newcommand\IncludeOnlyChapter[1]
  {
    \includeonly{\ContentsPath#1}
    }
}{}
```

### Create subsections chapterpath:

```latex
\newcommand\InputSection[1]
{
  \renewcommand\SectionPath{\ChapterPath#1/}
  \input{\ChapterPath#1}
}
```

### Add Subsection to path:

```latex
\newcommand\InputSubSection[1]
{
  \renewcommand\SubSectionPath{\SectionPath#1/}
  \input{\SectionPath#1}
}
```

### Add SubSection to path:

```
\newcommand\InputSubSubSection[1]
{
  \input{\SubSectionPath#1}
}
```

### Create a new chapter:

```latex
\@ifclassloaded{book}
{
  \newcommand\Chapter[1]
  {
    \chapter{#1}
    %\addcontentsline{toc}{chapter}{#1}
  }
}{}
```

### Add a line:

```latex
\newcommand\Section[1]
{
  \section{#1}%
  %\addcontentsline{toc}{section}{#1}
}
```

### Add SubSection to table of contents:

```latex
\newcommand\SubSection[1]
{
  \subsection{#1}
  %\addcontentsline{toc}{subsection}{#1}
}
```

### Add SubSubSection to table of contents:

```latex
\newcommand\SubSubSection[1]
{
  \subsubsection{#1}
  %\addcontentsline{toc}{subsubsection}{#1}
}
```

### Add the xcolor package:

`\RequirePackage{xcolor}`

### Add listings package and define lists:

```latex
\RequirePackage{listings}
\lstdefinestyle{Common}
{
  breaklines=true,
  tabsize=3,
  showstringspaces=false,
  aboveskip=0pt,
  belowskip=0pt,
  extendedchars=\true,
  language=PHP,
  frame=single,  
  %===========================================================
  framesep=3pt,%expand outward.
  framerule=0.4pt,%expand outward.
  xleftmargin=3.4pt,%make the frame fits in the text area.
  xrightmargin=3.4pt,%make the frame fits in the text area.
  %===========================================================
  rulecolor=\color{Red}% }
```

### Define a style:

```latex
\lstdefinestyle{ThemeA}
{
  style=Common,
  backgroundcolor=\color{Yellow!10},
  basicstyle=\scriptsize\color{Black}\ttfamily,
  keywordstyle=\color{Orange},
  identifierstyle=\color{Cyan},
  stringstyle=\color{Red},
  commentstyle=\color{Green}
}
```

### Add a new coding style:

```latex
\newcommand{\IncludeCode}[2][style=ThemeA]
{
  \lstinputlisting[#1,caption={\href{#2}{#2}}]{#2}
}
```

### Add links and hypcap packages:

```latex
\RequirePackage[colorlinks=true,bookmarksnumbered=true,bookmarksopen=true]{hyperref}
\RequirePackage[all]{hypcap}
```

### Add an index package makeidx:

`\RequirePackage{makeidx} \makeindex`

### Close the new book class `mybook`:

`\endinput`

## Step 3 - Create the main input file main.tex

This is a critical file. It is the main input file which you will compile to generate the project. It is called `main.tex`.

Create in the root of `MyProject` the `main.tex` file, then add the following content to the file.

```

\documentclass[dvipsnames,cmyk,12pt]{mybook}
\usepackage[a4paper,vmargin=15mm,hmargin=10mm]{geometry}

\title{Introduction to LaTeX}
\author{Your Name}
\date{\today}

%\IncludeOnlyChapter{Variables}

\begin{document}
\frontmatter
        \maketitle
        \thispagestyle{empty}
        \tableofcontents
    \lstlistoflistings
\mainmatter
        \part{Part 1}
                \IncludeChapter{Variables}
                \IncludeChapter{Array}
        \part{Part 2}   
                \IncludeChapter{Interface}
                \IncludeChapter{SubClass}
        \appendix\renewcommand{\chaptername}{\appendixname}
        \part{Appendix}
                \IncludeChapter{YourAppendix}
\backmatter
        \printindex
\end{document}
```

## Step 4 - Create a Variables file

Create a file for chapter `Variables` called `Variables.tex` and save it to `MyProject\Contents`

```

\Chapter{Variables}
\InputSection{Declaration}
\InputSection{Instantiation}
```

## Step 5 - Create Variables Directory

Create a directory within the `MyProject\Contents\` and name it `Variables`.

## Step 6 - Create a Declaration file

Create a file to hold a Declaration section and call it `Declaration.tex`. Then save it in `MyProject\Contents\Variables`.

```latex
\Section{Declaration}

\IncludeCode[style=ThemeA]{Codes/Declaration.php}
```

## Step 7 - Start creating topics

You can now start writing your topics for the project. Remember to save the files as .tex file and save to the `MyProject\Content\` directory.

## Finalize - Generate output

Here is an output from this skeleton project.

<img class="img" src="{{ baseurl }}/assets/img/latex/2-0-skeleton.png" alt="Output from the LaTeX skeleton project" >

[Next: LaTeX commands overview](/latex/latex-commands-syntax.html)
