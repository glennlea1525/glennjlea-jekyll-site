---
layout: article
title: Defining and using colours
type: latex
excerpt: By setting colour definitions in the stylesheet, you can reference them throughout the stylesheet or in the document.
date: '2020-04-23'
section: latex
categories:
  - latex
---
# {{ page.title }}


* Do not remove this line (it will not be displayed)
{:toc}

By setting colour definitions in the stylesheet, you can reference them throughout the stylesheet or in the document. For example,if you need to use corporate colours, you can then use these colours in your documentation, such as on the title page or in the headers or footers. The `color` anc `xcolor` packages are available for colour definitions. 


## color and xcolor packages

Before defining colours, you add the `colour` and `xcolor` packages. The `color` package provides basic colours to your document. You add it using the following command.

```latex
\usepackage{color}
% \usepackage{xcolor} Note: commented out
```

The `xcolor` package allows you to define custom colours using one of the colour models such as gray, rgb, cmyk, and so on. Use the `xcolor` package if you want to define colours based on corporate branding.

Note: If you use the `xcolor` package, comment out the `color` package.

## Setting up xcolor for the document

You can define `xcolor` for use in your document as follows:

`\usepackage[usenames,dvipsnames,svgnames,table]{xcolor}`

* `usenames` is one of the following sixteen predefined colours:

    black, blue, brown, cyan, darkgray,
    gray, green, lightgray, lime, magenta,
    olive, orange, pink, purple, red,
    teal, violet, white, yellow.

* `dvipsnames` loads a set of predefined colours.

* `svgnames` loads a set of predefined colours based on SVG definitions.

* `table` loads a predefined set of colours for use in table rows, columns and cells.

## Defining custom colours

Once you add the `xcolor` package, you can create a set of custom colours that can be used throughout the document. You use the `/definecolor` command with the colour type and settings as arguments, as shown below.  

`\definecolor{name}{colour model}{specification}`

The xcolor package provides many more options. I found that I only needed to use the rgb model, give the new colour a name and define its rgb values. 

For example, if you wanted to define a colour for use on the title page, give it a descriptive name, provide a colour model, and then provide colour values.

`\definecolor{mynewcolor}{RGB}{25,25,25}`

## Defining colours for the title page

You can define for the package `xcolor` color settings for the title page, such as the following example.

```latex
\definecolor{titlepagecolor}{RGB}{0,38,75} % Blue
\definecolor{namecolor}{RGB}{241,133,0} % Orange
```

The colours are given names so you can refer to them within the document. In the colour definitions, these are `titlepagecolor` and `namecolor`.

## Defining general use colours

You can then define some colour settings for use in various elements in the document. You can then use the given names within the stylesheet and document, for example `blue`, `orange`, `gray` or `codeBackground`. Note that I have defined two colours for `codebackground`. This allows me to switch between colours as needed by commenting one of the out.

```latex
\definecolor{blue}{rgb}{0,38,75} % Blue
\definecolor{orange}{rgb}{241,133,0} % Orange
\definecolor{gray}{rgb}{0.4, 0.0, 0.4} % Gray
\definecolor{codeBackground}{RGB}{251, 251, 244} % background color for code boxes
%\definecolor{codeBackground}{white} % White
```

## Summary of colour definitions

Here are the colours that I defined for use on the title page, headers and footers and other elements. Note that they all use the rgb colour model.

```latex
\definecolor{blue}{rgb}{0,38,75}                 % Blue: title page
\definecolor{orange}{rgb}{241,133,0}             % Orange: headers/footers/headings
\definecolor{gray}{rgb}{0.4, 0.0, 0.4}           % Gray: as required.
\definecolor{codeBackground}{RGB}{251, 251, 244} % Code box background colour
\definecolor{codeBackground}{white}              % White: as required.
```

## Defining colours for information Boxes

You can define background colour settings and line colour settings for information boxes used in the document.

```latex
\definecolor{warning}{RGB}{255,231,231}   % Background for Warning Box
\definecolor{note}{RGB}{255,255,211}      % Background for Note Box
\definecolor{info}{RGB}{224,239,255}      % Background Info Box
\definecolor{infoline}{RGB}{158,182,212}  % Line Color for Info Box
\definecolor{noteline}{RGB}{247,223,146}  % Line Color for Note Box
\definecolor{warnline}{RGB}{51,51,51}     % Line Colors for Warning Box
\definecolor{warnline}{RGB}{155,231,231}  % Additional line color for Warning Box
```

## Using colour definitions

Once you have defined a colour, you can using it within other styles or commands in the stylesheet.

For example, you can define an orange colour for chapter titles.

`\definecolor{chaptertitlecolor}{RGB}{232,134,12}`

Then this colour can be referenced in the style for chapter titles.

```latex
\titleformat{\chapter}
  {\fontsize{20pt}{0em}
  \selectfont\bf\color{chaptertitlecolor}}
  {\thechapter.}{1em}{}
```

If you want to change the colour of chapter titles then you need only change the definition of `chaptertitlecolor`.

[Next: Warning, Note and Info Boxes](/latex/warning-note-info-boxes.html)
