---
layout: article
title: Selecting the Document Class
type: latex
excerpt: The documentclass command tells the LaTeX typesetter how to handle the document and which document package to use to typeset the output.
date: '2020-03-29'
section: latex
categories:
  - latex
---
# {{ page.title }}


* Do not remove this line (it will not be displayed)
{:toc}

At the head of every LaTeX project file (`main.tex`) is the `\documentclass` command. In the following example, the `\documentclass` command tells the LaTeX typesetter how to handle the document and which document package to use to typeset the output. It also tells the typesetter to find the styles for the document in the location indicated.

```latex
% Copyright Glenn J Lea
% Name of Document and Version
%
% MAIN FILE
%
\documentclass[a4paper,11pt,twoside]{book}
\usepackage{styles/styles-template}
\begin{document}
```

These two commands are probably the most important decision you need to make for creating technical documentation using LaTeX: which type of document class and where to find the document styles.

## Selecting a document class

After looking at several types of document classes, I settled on the `book` class as the best fit to do the job.

Other documentclass types did not have the capability to output long documents with proper headers and footers and all the required elements of a professional quality technical document.

### book document class

After it seems like forever searching for that ideal class for technical documents, the solution was staring me in the face. The basic `book` class had all the requirements I needed. It was customizable and it was designed specifically for books, that is, long documents.

**Note:** Information about the _book_ class is available <a href="https://www.ctan.org/pkg/book?lang=en">here</a>.

### memoir document class

I also looked at the `memoir` documentclass. The author of this class, Peter Wilson, describes the memoir class as best suited for *type­set­ting po­etry, fic­tion, non-fic­tion, and math­e­mat­i­cal works.* It can use a wide range of font sizes, has quite a number of page styles to choose from as well as chapter styles to customize your document. It is very useful.

I tried to use this class first, but it just didn't suit my needs. I needed more flexibility in designing my title pages, adding headers and footers, and so forth. Frankly, I can't remember all the reasons why I didn't choose `memoir`, but in the end, it just didn't suit my needs.

**Note:** Information about the _memoir_ class is available <a href="https://www.ctan.org/pkg/memoir?lang=en">here</a>.


## Setting up the documentclass command

As shown above, you set the `\documentclass` in the document root file (`main.tex`) at the top of the file:

`\documentclass[a4paper,11pt,twoside]{book}`

This command includes a number of options. I

- `class` is set at the end of the command within the curly brackets - `{book}
- `arguments` are included within the square brackets - `[a4paper,11pt,twoside]`

It tells the LaTeX typesetter to use the built-in book class and output a document with an A4 paper size, use an 11pt font as the base font and use double-sided printing.

### Setting the Paper Size

As I was producing the document for European audiences, the paper size needed to be A4. You can choose `letter` for North American audiences.

- `a4paper` sets the page size to 210 × 297 millimeters or 8.27 × 11.69 inches.

### Setting the Base Font Size

 A good readable base font size is 11 points. 10 points or 9 points is too small for technical documentation. These documents are used by people in a hurry or having difficulty or wanting to know how to do some task. Why strain their eyes on a very small font size. Of course, if you are producing the document for online viewing, you need to adjust this accordingly, say perhaps 12 or 14 pts.

- `11pt` which is quite readable for user documentation.

### Setting Pagination

I want the typesetter to paginate on two sides so I don't end up with blank pages after each page. Setting two-sided makes the document doublesided, but DOES NOT tell the printer to print double-sided. This is important for page numbering, chapter titles and section titles in headers and footers. The book class is double-sided by default.

- `twoside` which makes the document double-sided, which means the margins on the left and right pages are mirrored.

## Including a stylesheet

Stylesheets are discussed in detail in a later topics. Rather than adding all the styles in the head section of main.tex, you can put them all in a stylesheets document and then reference the file in main.tex. This way you can have several stylesheets and comment out stylesheets you are not using.

[Next: Using Input/Include Commands](/latex/input-or-include-commands.html)
