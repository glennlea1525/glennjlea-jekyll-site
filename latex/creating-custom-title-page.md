---
layout: article
title: Creating custom title pages
type: latex
excerpt: LaTeX has the capability of defining quite good looking title pages.
date: '2020-04-24'
section: latex
categories:
  - latex
---
# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

LaTeX has the capability of defining quite good looking title pages. Not easy but doable. LaTeX comes with a standard title page, but you can create your own custom title page. Using the settings in this topics, you can create a title page similar to the following. The background is a dark blue while the text is an orange colour. It makes for a striking colour contrast for the title page, but a white colour would be just as good, if not better. However, what is set here is a branding colour

<img class="img" src="{{ baseurl }}/assets/img/latex/titlepage.png" alt="Sample title page" >

## Creating a title page

Here is the source that created the title page shown above.

```latex
\typeout{} % Typeout to terminal
\typeout{=====================================================================}
\typeout{==== Titlepage}
\typeout{====}
\typeout{==== titlepage.tex}
\typeout{=====================================================================}
\typeout{}

{
\begin{titlepage} % Opening environment

% Add the cover to TOC so it becomes the home link
\addcontentsline{toc}{chapter}{Sample Manual}

% Set the page margins
\newgeometry{left=5cm,top=6cm} 

% Set the background colour
\pagecolor{titlepagecolor}

% Remove indentations so margin is reference point
\noindent

% Place company logo at specified location
\includegraphics[width=10.91cm, height=2.33cm]{images/logo.png}\\[-1em]

% Set default background colour
\color{white}

% Create a frame box
\makebox[0pt][l]{\rule{1.3\textwidth}{1pt}}

% Add a paragraph in this box
\par

% Remove indentation so paragraph starts on left-side
\noindent

% Add some text to top of page
\textcolor{namecolor}{\large\textsf{User Guide}}

% Add spacing between top text and title
\vfill

% Add document title
{\huge \textsf{ACME Road Runner Catchment Device}}
\vskip\baselineskip
\noindent
\textcolor{namecolor}{\large\textsf{\PSDATE{}}}\\[0.25cm]
\textcolor{namecolor}{\large\textsf{Copyright \copyright \ Glenn J. Lea}}

% Restore geometry and end the title page
\restoregeometry 
\end{titlepage}
}

% Finally, restores page colour to white (no colour)
\clearpage
\pagecolor{white}
```

## Adding the title page in project root file

When you create a title page, such as `titlepage.tex`, place it in its own subdirectory of the project directory. Then in the project root file use the `\include` command to add the title page to the project output. 

```latex
\frontmatter{}
\fancyhead[RE,LO]{}
\include{files/titlepage}
\include{files/frontmatter}
\include{toc}
\clearpage
```

Note: The `\fancyhead` command is defined within the stylesheet.

## Defining the title page colours in the stylesheet

First add the `xcolor` package. Next, define the colours that will be used on the title page. Of course, the background colour on the title page can be white and text colour can be black, but you can set them to whatever you want as a defined colour. 

```latex
\usepackage{xcolor}
\usepackage{lipsum}% Used for dummy text.
\definecolor{titlepagecolor}{RGB}{0,38,75} % Prussian Blue
\definecolor{namecolor}{RGB}{232,134,12} % Orange
```

## Include the number of Table of Contents levels

Before you include the command `\input{subdir/titlepage.tex}` the typesetter needs to know the depth of the Table of Contents. You do this using the following command. In this example it is set to three levels.

`\setcounter{tocdepth}{2}`

[Next: Generating output from a LaTeX project](/latex/generating-output-latex-files.html)
