---
layout: article
title: Adding and defining fonts
type: latex
excerpt: Define the base font for your LaTeX documents.
date: '2020-04-22'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

## Introduction

You can add to the stylesheet settings for a document's base font, font size and monospaced fonts. This allows these settings to be used in any document that uses the stylesheet. Setting fonts, however, in LaTeX is not an obvious task. It is, to be honest, rather cumbersome. So, let's start with the basics. Fonts are packages which you add using the `\usepackage` command. For example, `\usepackage{helvet}`.

<div class="note">Note: For more information about about using fonts in LaTeX, see <a href="https://www.tug.org/pracjourn/2006-1/schmidt/schmidt.pdf">Font selection in LaTeX: The most frequently asked questions</a> - PDF file. </div>

## Setting base fonts for the entire document

For a project I typically use several fonts. For example, I used `Helvetica` for the base font and then I used `Latin Modern` as an alternate base font. `Latin Modern` is a set of true handmade vector fonts. 

In the stylesheet, I added the following commands. The first two set the base fonts for the document while the third changes the default family to sans serif.

```latex
\usepackage{helvet}                        % Base font for document
\usepackage{lmodern}                       % Alternate base font
\renewcommand{\familydefault}{\sfdefault}  % Changes the default family to Sans Serif
```

## Using font declarations

You can add font declarations that are valid within the current scope in the document. A declaration means that the font remains in effect until the end of the current group or environment. They are unlike defining a font in stylesheet which are used throughout the document. 

Font families, series and shapes can be combined in a single command. For example, the command `\bfseries\itshape` results in bold italic type.

### Select pre-defined font families

You first add font declarations to allow you to select between pre-defined font families. Then within each font family you add declarations to select the type of font, such as weight, form, and so on.

```latex
\rmfamily  % Selects a roman family
\sffamily  % Selects a san serif family
\ttfamily  % Selects a monospaced font
```

### Add a declaration

You then add the following declarations within each font family by using the following:

```latex
\mdseries   % Format the font as regular to keep the font as it is.
\bfseries   % Bold the font.
```

### Examples

Text strings can be formatted using the following:

```latex
\upshate  % reverts the text back to normal
\slshape  % forward slants the text
\itshape  % italicizes the font
\scshape  % makes the text All Caps and Small Caps
```

## Using the Micriotype package

To improve readability, you can add the Microtype package. When used, you need to define some options and settings. For example, the PostScript font Adobe Courier is used for monospaced text.

```latex
\usepackage{microtype}
\usepackage{courier}
```

## Allowing relative font sizes

To allow relative font size specifications, (e.g. \smaller, \larger) use the the package `relsize`.

`\usepackage{relsize}`

## Setting fonts for table of contents

To control the fonts and formatting used in the Table of Contents, use the `titles` package and set the argument `tocloft`.

`\usepackage[titles]{tocloft}`

## Redefine line spacing

You can redefine the spacing to make the text more aesthetically appealing.

```latex
\setlength{\cftbeforechapskip}{2ex}
\setlength{\cftbeforesecskip}{0.5ex}
```

## Making dummy text available

You can make dummy text available to use in the document with the lipsum package.

`\usepackage{lipsum}`

[Next: Adding multi-lingual support](/latex/adding-multi-lingual-support.html)
