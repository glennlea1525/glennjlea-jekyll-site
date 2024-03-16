---
layout: article
title: Customizing headers and footers
type: latex
excerpt: Using the fancyhdr package, you can create customized headers and footers.
date: '2020-04-24'
section: latex
categories:
  - latex
---
# {{ page.title }}


* Do not remove this line (it will not be displayed)
{:toc}

Page headers and footers in LaTeX are defined by the `\pagestyle` and `\pagenumbering` commands.

- `\pagestyle` defines the general contents of the headers and footers, such as where the page numbers will be printed.

- `\pagenumbering` defines the format of the page number.  

Using the `fancyhdr` package, you can create customized headers and footers. I have added this to the stylesheet so it can be applied to all chapters in the project.

## Defining headers and footers

To customize headers and footers, you can use the `fancyhdr` package, which is used with the page style `fancy`. Rather than using the default headers and footers, `fancyhdr`enables custom headers and footers for odd and even pages, for chapter pages and to allow for control over font sizes, as well as much more.

The following commands defines the headers and footers of the document.

```latex
\usepackage{fancyhdr}
\pagestyle{fancy}
\fancyhf{}

\renewcommand{\helv}{\fontfamily{phv}
  \color{titlepagecolor}
  \fontseries{b}
  \fontshape{n}
  \fontsize{9}{11}\selectfont}

\renewcommand{\chaptermark}[1]{\markboth{\helv\NoUppercase{#1}}{}}
\renewcommand{\sectionmark}[1]{\markright{\helv\NoUppercase{#1}}{}}
\renewcommand{\sectionmark}[1]{\markright{\helv\thesection.\ #1}}
\renewcommand{\chaptermark}[1]{\markboth{\helv\thechapter.\ #1}{}}

\renewcommand{\headrulewidth}{0pt}
\renewcommand{\footrulewidth}{0pt}

\fancyfoot[LE,RO]{\helv Page \thepage}
\fancyfoot[RE,LO]{\helv Copyright \copyright 2020 Glenn J. Lea Confidential}

```

These commands are explained in the following sections.

**Note:** Information about the `fancyhdr` package is available <a href="http://www.ctex.org/documents/packages/layout/fancyhdr.pdf">here</a>.

## Font definitions

In the following set of commands, the font is defined as 9 pt Helvetica using the short form `phv`. The text of the headers and footers use the `titlepagecolor` for the background.

```latex
\renewcommand{\helv}{\fontfamily{phv}
\color{titlepagecolor}
\fontseries{b}
\fontshape{n}
\fontsize{9}{11}\selectfont}
```

Note that the `titlepagecolor` has been defined elsewhere in the stylesheet using the `definecolor` command.

```latex
\definecolor{titlepagecolor}{RGB}{0,38,75}
```

## Injecting chapter and section text into the header

The text of a chapter heading is injected into the header using `\chaptermark`. `\thechapter` pulls in the chapter number. Similarly, the text of the section heading is pulled in using `\sectionmark`. The macro `thesection` pulls in the number of the section.

```latex
\renewcommand{\chaptermark}[1]{\markboth{\helv\NoUppercase{#1}}{}}
\renewcommand{\sectionmark}[1]{\markright{\helv\NoUppercase{#1}}{}}
\renewcommand{\sectionmark}[1]{\markright{\helv\thesection.\ #1}}
\renewcommand{\chaptermark}[1]{\markboth{\helv\thechapter.\ #1}{}}
```

## Eliminating horizontal lines

If you don't want to have a decorative line to separate the header from the body text, set the header and footer rule width to 0pt.

```latex
\renewcommand{\headrulewidth}{0pt}
\renewcommand{\footrulewidth}{0pt}
```

## Defining footer text

If you want the footer to have only a page number and a copyright notice on each page, use the following commands.

```latex
\fancyfoot[LE,RO]{\helv Page \thepage}
\fancyfoot[RE,LO]{\helv Copyright \copyright 2021 Glenn J. Lea. Confidential}
```

## Inserting fancyhead into the root file

After defining the headers and footers in the stylesheet, you insert the header into the root file after the `\frontmatter` environment command as follows.

```latex
\begin{document}

\frontmatter

% Configuration of the header strings for the frontmatter pages.
\setcounter{tocdepth}{3}
\fancyhead[RE,LO]{}
```

**Note:** It is important where you place this command. The LaTeX typesetter needs to know how to build the headers and footers before any geometry is defined. After calling the `\fancyhead` command, you can go ahead and input your files, and so forth.

## Header and Footer Example

The following shows the resulting pages with headers and footers.

<p><img class="img" src="{{ baseurl }}/assets/img/latex/header-footer-pg01.png" alt="Sample chapter page with header and footer" ></p>
<p class="center">Sample chapter page with header and footer.</p>

<p><img class="img" src="{{ baseurl }}/assets/img/latex/header-footer-pg02.png" alt="Sample even page" ></p>
<p class="center">Sample even page.</p>

[Next: Defining and using colours](/latex/defining-and-using-colours.html)
