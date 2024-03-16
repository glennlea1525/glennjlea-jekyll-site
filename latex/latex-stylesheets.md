---
layout: article
title: Creating LaTeX Stylesheets
type: latex
excerpt: Use a stylesheet to easily maintain all the styles used by your LaTeX project.
date: '2020-04-14'
section: latex
categories:
  - latex
---
# {{ page.title }}


* Do not remove this line (it will not be displayed)
{:toc}

The key development effort to create high-quality technical documentation is the stylesheet. It takes a considerable amount of time to develop but getting it right is critical for the quality of the documentation.

Using a LaTex stylesheet makes it easy to keep in one place all the styles used by the document. Stylesheets are a useful method of organizing all the styles used throughout your LaTeX project. You could also have a single stylesheet file, `stylesheet.sty` for example, that is used across multiple projects.

## Why Use a stylesheets?

You could put all your styles in the head of each `.tex` file in your project but that makes no sense, especially if you have multiple files referring to the same stylesheet. Furthermore, keeping all your styles in a single file makes maintaining the styles vastly easier. For example, you could comment out particular commands to help you during your development process. You could also comment out chapters that are not required for specific documents, such as reference material or list of terminology.   

## Project structure that includes a styles subdirectory

For my LaTeX projects, I created a subdirectory called `\styles`and I placed in this directory a single style sheet called `mystyles.sty`. If more than one stylesheet is required for your project, then they can be placed in this subdirectory. 

Here is an example project structure. Notice the `\styles` directory.  

    Project Root
    ├── manual-ROOT.tex        # document root file
    ├── \styles                # stylesheet subdirectory
    ├── \chapters              # subdirectory to store all chapters
    ├── \append                # subdirectory to store any appendices
    ├── \images                # subdirectory for shared images

## Including the stylesheet in the root file main.tex

To use the stylesheet in your project, you simply include a command in the root file `main.tex` immediately following the `\documentclass` command but before the `\begin{document}` command.

Here is an example snippet from a `main.tex` file.

```latex

% Copyright Glenn J. Lea
%
% MAIN FILE
%
% Set the document class which is book
\documentclass[a4paper,11pt,twoside]{book} 
% Insert the stylesheet
\usepackage{styles/mystyles}
% Begin the document
\begin{document}   
```

## Example stylesheet

To help you get started creating a stylesheet for your project, here is an short example you can begin with. I kept all related styles together within sections separated by comments. 

### Packages

First, include required packages. 

```latex
% Packages
  \usepackage[T1]{fontenc}
  \usepackage{amsmath}
  \usepackage{amssymb,amsfonts,textcomp}
  \usepackage{hhline}

% Creates custom columns
  \usepackage{array}

% Create links for clickable URLs
  \usepackage{hyperref}

% Langauge selection to US English
  \usepackage[english]{babel}

% Standard graphics support.
  \usepackage{graphicx}
```

### Base fonts and text formatting

Second, define a base font and format specifications for text.

```latex
% Font Selection Styles and Packages, where Helvetica is the base font.
  \usepackage{lmodern}
  \usepackage{helvet}
  \renewcommand{\familydefault}{\sfdefault}

% Monospaced font
  \usepackage{courier}

% Allow relative size specifications, for example \smaller, \larger.
  \usepackage{relsize}

% Table of contents fonts and formatting
  \usepackage[titles]{tocloft}

% Redefine spacing
  \setlength{\cftbeforechapskip}{2ex}

  \setlength{\cftbeforesecskip}{0.5ex}

% Text styles
  \newcommand\textstyleCourier[1]{\texttt{#1}}
  \newcommand\textstyleDefaultParagraphFont[1]{#1}
  \makeatletter
  \newcommand\arraybslash{\let\\\@arraycr}
  \makeatother
```

### Title Page

Third, define the layout of the document's title page. 

```latex
% Title page packages and colour settings
  \usepackage{xcolor}
  \usepackage{lipsum}  % Used for dummy text.
  \definecolor{titlepagecolor}{RGB}{0,38,75}
  \definecolor{namecolor}{RGB}{241,133,0}

% General use colour definitions
  \definecolor{blue}{rgb}{0,38,75}
  \definecolor{orange}{rgb}{241,133,0}
  \definecolor{gray}{rgb}{0.4, 0.0, 0.4}
  \definecolor{codeBackground}{RGB}{251, 251, 244}
  \definecolor{codeBackground}{white}
```

### Warnings, Notes and Info boxes colours

Fourth, define the background and line colours for boxes for warnings, notes and additional information. 

```latex
% Background Colors
  \definecolor{warning}{RGB}{255,231,231} % Warning
  \definecolor{note}{RGB}{255,255,211} % Note
  \definecolor{info}{RGB}{224,239,255} % Info

% Line Colors
  \definecolor{infoline}{RGB}{158,182,212} % Info
  \definecolor{noteline}{RGB}{247,223,146} % Note
  \definecolor{warnline}{RGB}{51,51,51} % Warning
```

### Heading styles

Fifth, define the packages and formatting of headings. 

```latex
% Sectioning Styles and Packages
  \usepackage{titlesec}
  %\usepackage{sectsty}

% Chapter heading redefinition

% Redefine size and position of chapter heading
  \titleformat{\chapter}
    {\fontsize{19pt}{0em}\selectfont\bf}
    {\thechapter.}{1em}{}

% Change colour of chapter heading
  \titleformat{\chapter}
    {\fontsize{20pt}{0em}\selectfont\bf\color{namecolor}}
    {\thechapter.}{1em}{}

% Redefine spacing above chapter heading
  \titlespacing*{\chapter}{0pt}{-30pt}{20pt}

% Indent Section label
  \titlelabel{\llap{\makebox[1cm][l]{\thetitle}}\hspace*{25.4mm}}
```

### Section definitions

Sixth, define the fonts and layout of document sections, subsections and subsubsections. LaTex has default settings for these elements, so what you need to do is redefine these settings. 

```latex

% Redefine font size of Section heading
  \titleformat{\section}[hang]
    {\normalfont\Large\bfseries\color{namecolor}}
    {\thesection.}{1em}{}

% Redefine spacing above Section heading
  \titlespacing{\section}{0pt}{*4}{*1.5}      

% Redefine size and position of Subsection heading
  \titleformat{\subsection}[hang]
    {\normalfont\Normalsize\bfseries\color{namecolor}}
    {\thesubsection.}{1em}{}

% Redefine size and position of subsubsection heading
  \titleformat{\subsubsection}[hang]
    {\normalfont\Normalsize\bfseries\color{namecolor}}
    {\thesubsubsection.}{1em}{}
```

### Page size, margin and layout definitions

Seventh, perhaps the most important settings are here in the page size and margins. This needs to be carefully prepared. On the other hand, you can just copy and paste the following for an A4 page with relatively sufficient margins for readability. 

```latex
% Package
  \usepackage[vcentering,dvips]{geometry}
  \geometry{papersize={210mm,295mm},total={160mm,185mm}}

% Defining page layout (geometry)
   \setlength\voffset{-1in}
   \setlength\hoffset{-1in}
   \setlength\topmargin{1cm}
   \setlength\oddsidemargin{3cm}
   \setlength{\evensidemargin}{3cm}

% Text height original: 24.5, new: 23.5cm
  \setlength\textheight{23.5cm}

% Text width original: 16cm, new 15 cm
  \setlength\textwidth{15cm}
  \setlength\footskip{1.0cm}
  \setlength\headheight{1cm}

  \setlength\headsep{1cm}

  \setlength{\parindent}{0cm}
  \setlength{\parskip}{3pt}
```

**Note:** The following topics refer to this stylesheet.

[Next: Adding and defining fonts](/latex/adding-defining-fonts.html)
