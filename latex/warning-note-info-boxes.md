---
layout: article
title: Warning, Note and Info Boxes
type: latex
excerpt: Define styles for notes, info and warning boxes
date: '2020-04-29'
section: latex
categories:
  - latex
---
# {{ page.title }}


* Do not remove this line (it will not be displayed)
{:toc}

Custom formatted framed boxes for notes, warnings and additional information can be included in the document based on styles you define in the Stylesheet. These same definitions can be used to insert basic boxes for general use. 

You then insert the appropriate box type in the document using a simple command.

## Adding table- related packages

These framed boxes use a type of table that is provided in the `supertabular` and `tikz` packages. You need to add these packages before adding the packages for framed boxes. You add them as shown below.

```latex
\usepackage{supertabular} 
  % Adds the supertabular type of table
% \usepackage{xcolor} 
  % Adds the xcolor package
\usepackage{tikz} 
  % This package modifies the framed boxes
% \usepackage{longtable} 
  % Adds the longtable type of table which breaks across pages
% \usepackage{tabulary} 
  % Adds the tabulary type of table
% \usepackage{colortbl} 
  % Use for table colouring
```

## Defining a custom framed box

Before you define the specific boxes, you need to add some packages and define some colours. Add the following to your stylesheet and change the RGB values to what you need.

Note: You can keep all the colour definitions organized by including them within the Colours section of the stylesheet.

```latex
\usepackage{framed, multicol, color} 
  % Packages for creating a framed multicolumn box
\definecolor{shadecolor}{RGB}{216,228,241} 
  % First shading colour
\definecolor{shadecolor1}{RGB}{216,228,241} 
  % Second shading colour
\usepackage[framemethod=tikz]{mdframed} 
  % Allows for tikz options for the frame
\usetikzlibrary{calc} 
  % Adds the calculation library
\usetikzlibrary{shadows} 
  % Adds the shadows library
```

With these settings, each type of box can now be defined in the stylesheet.

## Defining a basic boxes

You can define a general purpose box for use as required.

The following defines the rules, spacing, icon and background colour of a warning box. You can just copy and adjust these settings as needed. This give the name of this rule `{basic}` which you find at the end of this definition.


```latex
% Redefine the environment for a Basic box using the following:
\newmdenv[
  roundcorner=10pt,
  skipabove=10pt
  skipbelow=10pt
  leftmargin=10pt,
  rightmargin=10pt,
  backgroundcolor=codeBackground,
  innertopmargin=20pt,
  innerbottommargin=20pt,
  innerleftmargin=20pt,
  innerrightmargin=20pt,
  middlelinewidth=0pt,
  everyline=true,
  linecolor=warnline,
  font=\normalfont\normalsize,
  shadow=false,
  frametitlefont=\normalfont\normalsize\bfseries,
  frametitleaboveskip=1em,
  singleextra={
%   \node[inner sep=0pt,anchor=north west,xshift=10pt,yshift=-30pt] 
         at (P-|O);
    \node[inner sep=0pt,anchor=north west,yshift=-.8\baselineskip,
         font=\bfseries,xshift=10pt] at (P-|O) { };    
  },
  firstextra={
%   \node[inner sep=0pt,anchor=north west,xshift=10pt,yshift=-30pt] at (P-|O);
    \node[inner sep=0pt,anchor=north west,yshift=-.8\baselineskip,
         font=\bfseries,xshift=10pt] at (P-|O) { };    
  }
]
% Define the name of the framed box
{basic}                     
```
## Inserting a basic box in a document

Use the following to insert a basic box into the document flow. I usually just copy and paste it into the document where I need it and then replace the placeholder text with my text. 

```latex
\begin{basic}
Basic text placeholder
\end{basic}
```


## Defining Warning boxes

A Warning Box is information that a user must be aware of before performing a specific task.

The following defines the rules, spacing, icon and background colour of a warning box. You can just copy and adjust these settings as needed. This give the name of this rule `{warnbox}` which you find at the end of this definition.

```latex
% Redefine the environment for the Warning framed box
\newmdenv[
  roundcorner=10pt,
  skipabove=10pt
  skipbelow=10pt
  leftmargin=20pt,
  rightmargin=20pt,
  backgroundcolor=warning,
  innertopmargin=30pt,
  innerbottommargin=10pt,
  innerleftmargin=70pt,
  middlelinewidth=0pt,
  everyline=true,
  linecolor=warnline,
  font=\normalfont\normalsize,
  shadow=false,
  frametitlefont=\normalfont\normalsize\bfseries,
  frametitleaboveskip=1em,
  singleextra={
    \node[inner sep=0pt,anchor=north west,
      xshift=10pt,yshift=-30pt]
      at (P-|O){\includegraphics[scale=0.40]{sharedimages/alerticon}};
    \node[inner sep=0pt,anchor=north west,
      yshift=-.8\baselineskip,font=\bfseries,xshift=10pt]
       at (P-|O)
     {Warning};    
  },
  firstextra={
    \node[inner sep=0pt,anchor=north west,
      xshift=10pt,yshift=-30pt] at (P-|O)
    {\includegraphics[scale=0.40]{sharedimages/alerticon}};
    \node[inner sep=0pt,anchor=north west,
      shift=-.8\baselineskip,font=\bfseries,xshift=10pt]
     at (P-|O)
     {Warning};    
  }
]
% Define the name of the framed box  
{warnbox}
```

## Inserting a Warning box in document

You insert a warning box into the document flow using the following commands.

```latex
\begin{warnbox}
Warning text placeholder
\end{warnbox}
```

## Defining Note boxes

Note Boxes are additional information that is important but outside the procedure described in the current text flow.

The following is essentially the same as defined for the Warning Box, with the exception of the background colour and the icon used in the box. This gives the name of the Note box as `notice`.

```latex
% Redefine the environment for Note boxes                     
\newmdenv[
  roundcorner=10pt,
  skipabove=10pt
  skipbelow=10pt
  leftmargin=20pt,
  rightmargin=20pt,
  backgroundcolor=note,
  innertopmargin=30pt,
  innerbottommargin=10pt,
  innerleftmargin=70pt,
  middlelinewidth=0pt,
  everyline=true,
  linecolor=warnline,
  font=\normalfont\normalsize,
  shadow=false,
  frametitlefont=\normalfont\normalsize\bfseries,
  frametitleaboveskip=1em,
  singleextra={
    \node[inner sep=0pt,anchor=north west,
      xshift=10pt,yshift=-30pt] at (P-|O)
    {\includegraphics[scale=0.40]{sharedimages/tipsicon}};
    \node[inner sep=0pt,anchor=north west,
      yshift=-.8\baselineskip,font=\bfseries,xshift=10pt] at (P-|O)
    {Note};    
  },
  firstextra={
    \node[inner sep=0pt,anchor=north west,
      xshift=10pt,yshift=-30pt] at (P-|O)
    {\includegraphics[scale=0.40]{sharedimages/tipsicon}};
    \node[inner sep=0pt,anchor=north west,
      yshift=-.8\baselineskip,font=\bfseries,xshift=10pt] at (P-|O)
    {Note};    
  }
]
% Define the name of the framed box  
{notice}                     
```

## Inserting a Note box in document

Use the following commands to insert a Note Box into the document flow.

```latex
\begin{notice}
Note text placeholder
\end{notice}
```

## Definition for Info boxes

An Info Box would normally be used to provide additional information that may be available outside the current document, such as a website or another user manual.

Like the Warning and Note Box definitions above, you can adjust the settings as required. This gives the name of the box `infobox`.

```latex
% Redefine the environment for Info boxes                     
\newmdenv[
  roundcorner=10pt,
  skipabove=10pt
  skipbelow=10pt
  leftmargin=20pt,
  rightmargin=20pt,
  backgroundcolor=info,
  innertopmargin=30pt,
  innerbottommargin=10pt,
  innerleftmargin=70pt,
  middlelinewidth=0pt,
  everyline=true,
  linecolor=warnline,
  font=\normalfont\normalsize,
  shadow=false,
  frametitlefont=\normalfont\normalsize\bfseries,
  frametitleaboveskip=1em,
  singleextra={
    \node[inner sep=0pt,anchor=north west,
      xshift=10pt,yshift=-30pt] at (P-|O)
    {\includegraphics[scale=0.40]{sharedimages/noticeicon}};
    \node[inner sep=0pt,anchor=north west,
      yshift=-.8\baselineskip,font=\bfseries,xshift=10pt] at (P-|O)
    {Information};    
  },
  firstextra={
    \node[inner sep=0pt,anchor=north west,
      xshift=10pt,yshift=-30pt] at (P-|O)
    {\includegraphics[scale=0.40]{sharedimages/noticeicon}};
    \node[inner sep=0pt,anchor=north west,
      yshift=-.8\baselineskip,font=\bfseries,xshift=10pt] at (P-|O)
    {Information};    
  }
]
% Define the name of the framed box
{infobox}                     
```

## Inserting a Info box in document

Use the following commands to insert an Info box into the document flow.

```latex
\begin{infobox}
Info text placeholder
\end{infobox}
```

[Next: Creating custom tables](/latex/creating-custom-tables.html)
