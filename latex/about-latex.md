---
layout: article
title: About LaTeX
excerpt: LaTeX comes "out-of-the-box well prepared to produce high-quality product documentation.
type: latex
section: latex
categories: latex
---


# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

## Why LaTeX?

Some time ago, a client requested that I use LaTeX to produce their set of documentation. After taking a deep breath and saying OK, I went about trying to figure out how to do this. At the time I had zero experience with this system. LaTeX is, after all, typically used to write academic and scientific writing and is not often used for high quality product technical documentation.

With a little work (actually a lot of work) LaTeX can produce quite reasonable technical documentation. However, it only is capable of outputting to PDF. I could be wrong on this, so if you know of a way of outputting to HTML, I'd love to hear about it.

If you are like me and had never used LaTeX before, learning this tool is all about research, trying out some ideas, reading some more, trying again and so on. You learn best by doing.

Frankly, LaTeX doesn't come "out of the box" very well prepared for creating professional level technical documentation. In fact, there is "no box" for it to come out of. LaTeX separates content from layout so you need to know the commands and markup language of LaTeX. You also need to know how to generate output. That makes it quite similar to Markdown or HTML, in a sense. 

## First, its Lah-tech

Incidentally, LaTeX is pronounced as "Lah-tech". Why? No idea.

LaTeX is a typesetting language "intertwined with LaTeX commands". Since it has been around a long time, many plugins, which are called **packages**, are available to customize the layout and design for a wide range of uses.

## Know your sources

Where to start? A fellow Canadian told me to start by going to the <a href="http://tug.org/" target="_blank">TeX User Group (TUG)</a> site. Good advice.

At TUG, you can download all the required software to set up a LaTeX publishing system on both MAC and Windows machines. As I wasn't sure which OS I would ultimately use, I set up LaTEX on both machines. The site has a _Getting Started_ page which I recommend reading. See <a href="https://tug.org/begin.html">Getting Started with TeX, LaTeX and Friends</a>

Some other useful resources include the _LaTeX Project Site_ (<a href="http://www.latex-project.org/">www.latex-project.org</a>), as is the _Comprehensive TeX Archive Network_ (<a href="http://ctan.org/">ctan.org</a>).

## LaTex syntax

For the purposes of this tutorial, we focus on only the following types of syntax for LaTex.

| Command | Description |
| --- | --- |
| `\`  | Commands begin with a backslash. For example: `\documentclass` |
| `{ }` | Command arguments are enclosed in curly braces. For example: `\documentclass{class}` |
| `[]` | Optional arguments are enclosed in square brackets and are placed before the command arguments. For example: `\documentclass[opt,opt,. . . ]{class}` |

[Next: Selecting a LaTeX distribution and editor](/latex/installing_distributions.html)
