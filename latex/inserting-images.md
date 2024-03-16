---
layout: article
title: Inserting images
type: latex
excerpt: You define in the stylesheet how images appear in the document.
date: '2020-04-30'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

You define in the stylesheet how images appear in the document using the `graphicx` package. You can add captions to images using the `caption` package.

## Adding the graphicx package

The `graphicx` pack­age pro­vid­es a key-value in­ter­face for optional arguments to the `\include­graph­ics` command.

Note: Do not use the other graphics package when using `graphicx`.

Add the `graphicx` package using the following command:

`\usepackage{graphicx}`

## Formatting images using the graphicx package

The `graphicx` pack­age builds upon the graph­ics pack­age pro­vid­ing a key-value in­ter­face for op­tional ar­gu­ments to the `\in­clude­graph­ics` com­mand.

This in­ter­face pro­vides fa­cil­i­ties that go far be­yond what the `graph­ics` pack­age of­fers on its own. Do not use the older graphics package when using `graphicx`.

`\usepackage{graphicx}`

Then you include an image in a .tex file using the following syntax:

`\includegraphics[scale=1]{images/logo.png}`

Here is another example:

`\includegraphics[width=10.91cm, height=2.33cm]{images/rgb_logo.png}\\[-1em]`

## Adding captions using the caption package

You can define captions using the `caption` package. For example, you can define how the captions are formatting using the following:

```latex
usepackage[font=small,format=plain,labelfont=bf,up,textfont=it,up]{caption}
```

This sets the font size to a LaTex defined small size and without any decoration.

Then you an insert an image in the document using the following syntax. Note that you do not need to include the image extension.

```latex
\begin{figure}[h!]  
    \centering
    \includegraphics[scale=.75]{images/Image-name}
  \caption{Caption of an image}
\end{figure}
```

## Insert images using includegraphics

Then insert an image within a text flow using `includegraphics`.

In the following example, the image is resized:

`\includegraphics[width=10.91cm, height=2.33cm]{images/logo.png}`

Note: The file extension can be omitted, but I prefer to keep the entire filename, including the extension.

In this example, the image is resized to the following values: set the width to 10.19 cm and set the height to 2.33 cm.

Alternatively, the image can be scaled.

`\includegraphics[scale=1.75]{images/logo.png}[-1em]`

Note: `[-1em]` is a positioning element, which moves the image 1em to the left of the defined left margin. This is a page design issue.  

You can optionally set the path to graphics using the `\graphicspath` command:

`\graphicspath{ {images/} }`

[Next: Inserting code snippets](/latex/inserting-code-snippets.html)
