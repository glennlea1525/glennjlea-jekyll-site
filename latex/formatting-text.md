---
layout: article
title: Commands for font formatting and lists
type: latex
excerpt: LaTeX provides commands for formatting text, creating lists and adding images.
date: '2020-04-29'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

LaTeX provides commands for formatting fonts and creating lists.

## Formatting fonts

To make sections of text use the following:

```latex
\B{...}  - bold
\I{...} - italic
\T{...} - monospaced
\TB{...} - monospaced bold
\TB{...} - monospaced italic
```

To format paragraphs use the following:

```latex
\textbf{Road Runner} - bold
\textit{ACME} - italics
\emph{ACME} - italics
\underline{Tunnel Ahead} - underlined
```

## Formatting ordered and unordered lists

When making an unordered list, you use `itemize`. When making an ordered list, you use `enumerate`.

Use `itemize`to create an unordered list as shown below.

```latex
\begin{itemize}
\item \textbf{Body} - The thing that holds the fins in the right place.
\item \textbf{Fins} - The things that steer the tunafish in the sea.
\item
\end{itemize}
```

Use `enumerate` to create ordered lists as shown below.

```latex
\begin{enumerate}
\item Get a boat
\item Get a fishing rod
\item Find fish
\item Open can of tuna fish
\item Cast the line out 
\item Reel in the tuna fish
\end{enumerate}
```

## Formatting nested Lists

Use the following commands to create nested lists.

```latex
\begin{enumerate}
\item \textbf{Body} - The thing that holds the fins
     \begin{itemize}
     \item The yummy part that you can eat
     \item Lots of bones and stuff that you cannot eat
     \item \textbf{Fins} - The things that steer the tunafish
        \begin{itemize}
        \item The fins are sometimes sharp
        \item Do not eat them
        \end{itemize}
     \end{itemize}
\end{enumerate}
```

## Resuming a list after paragraphs

I found it rather annoying that LaTeX didn't have an easy way of dealing with interrupted lists, until I learned this tip on StackOverflow.

Use the package `\enumitem` and the `[resume]` option on an `enumerate` scope to cause the LaTeX typesetter to continue numbering from the previous list.

First, add the `enumitem` package to the stylesheet for resuming enumeration after intervening text element.

`\usepackage{enumitem}`

Then in the text use `[resume]` to continue the list, as shown in the following example.

```latex
\begin{enumerate}
    \item List item
    \item Another list item
\end{enumerate}

A randomly inserted paragraph.

\begin{enumerate}[resume]
    \item Further item
    \item Final item
\end{enumerate}

Paragraph of comments on list items 1 and 2.

\begin{enumerate}[resume]
\item Further item
\item Final item
\end{enumerate}
\end{document}
```

[Next: Inserting images](/latex/inserting-images.html)
