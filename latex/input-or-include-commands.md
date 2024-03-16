---
layout: article
title: Using Input/Include Commands
type: latex
excerpt: In a root file, referencing chapter file can be done using either the include or the input commands.
date: '2020-04-12'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

Each chapter or section in the document is referenced in a root file using either the `\input` or the `\include` command. This has the added advantage of listing all the external chapter files in the `main` file and then by either commenting or uncomment them, include or exclude them to the output stream when generating a LaTex document.

**Note:** For more information about input and include and their differences, see this topic on tex.stackexchange.com: [When should I use input vs. include](https://tex.stackexchange.com/questions/246/when-should-i-use-input-vs-include).


## Using the input Command

The command `\input{filename}` imports a file such as `filename.tex` into the target file. It's equivalent to typing the content of `filename.tex` into the current file at the location of the `\input` line.

Additionally, the order in which the files are listed determines the order of the chapters or sections.

`\input{filename}`

For example, the following list of chapters use the `\input` command to insert the files into the typesetting stream for output.

```latex
%% Chapters inputs
\input{MANUAL/manual-ch01-preface.tex}
\input{MANUAL/manual-ch02-overview.tex}
\input{MANUAL/manual-ch03.tex}
\input{MANUAL/manual-ch04.tex}
\input{MANUAL/manual-ch05.tex}
\input{MANUAL/manual-ch06.tex}
\input{MANUAL/manual-ch07.tex}
\input{MANUAL/manual-ch08.tex}
\input{MANUAL/manual-ch09.tex}
\input{MANUAL/manual-ch10.tex}
\input{MANUAL/manual-ch11-troubleshooting.tex}
\input{MANUAL/manual-ch12-tutorials.tex}
\input{MANUAL/manual-ch13-faq.tex}
\input{MANUAL/manual-ch14-release-notes}
```

For most purposes, the `\input` command is sufficient. If you want more control over placement of content, then use the `\include` command.

## Using the include Command

The command `include{filename}` adds a `\clearpage` before and after the insertion of the LaTex file into the typesetting stream. This results in the chapter starting on a new page.

`\include{filename}`

For example, the following list of chapters use the `\include` command to insert the files into the typesetting stream for output but all starting on a new page in the document. 

```latex
\include{tex/preface}
\include{tex/intro}
\include{tex/chap01}
\include{tex/chap02}
\include{tex/summary}
```

[Next: Footnotes, widows and orphans](/latex/footnotes-widow-orphans.html)
