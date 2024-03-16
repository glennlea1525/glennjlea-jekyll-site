---
layout: article
title: Sample LaTeX file - Hello World
excerpt: Let's now take a closer look at the structure of a very simple LaTeX file, the classic Hello World file.
type: latex
date: '2020-04-30'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

In the <a href="/latex/1-3-quick-start-guide">Quick Start Guide</a>, we entered a sample LaTeX document in a LaTeX editor then built this file to generate a pdf. Let's now take a closer look at the structure of a very simple LaTeX file, the classic _Hello World_ file.

## Hello World

This simple LaTeX file includes the most basic requirements to output a file using LaTeX.

```latex
\documentclass{article}
\begin{document}
Hello world!
\end{document}
```

When you write a LaTeX document you are essentially giving commands to the LaTeX typesetter how to treat the information on each line, or blocks of lines.

## First line - class of document

The first line in this example tells the compiler that what follows is a type of document of class `article`.

```latex
\documentclass{article}
```

The compiler now knows what to expect and it has built-in macros to deal with this type of document (as well as many other types of LaTeX documents). It tells the compiler to use its `article` macros to build a layout and use the content.

## Second line - begin document

After this command, you then need to tell the compiler that the document is beginning.

```latex
\begin{document}
```

## Document content

Afterwards, you give the compiler the content of the document, which in this case is quite uninspiring.

```latex
Hello World!
```

## Final line - end of document

Then you have to tell the compiler that the document is finished.

```latex
\end{document}
```
That's it! You can go ahead and try this using TeXworks. A pdf file is generated using the default font, layout and so forth. Like the input, the output is uninspiring.

## Summary

Of course, for creating a technical document much more detail is required. But these elements form the basic structure of a simple LaTeX file.

[Next: LaTeX skeleton structure](/latex/basic_latex_skeleton_file.html)