---
layout: article
title: Adding multi-lingual support
type: latex
excerpt: Use the babel package for setting the language of the document.
date: '2020-03-08'
section: latex
categories:
  - latex
---

# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

You can set the language for the document using the `babel` package. This  pack­age man­ages language-based ty­po­graph­i­cal (and other) rules as well as hyphenation pat­terns for a wide range of languages.

You can se­lect a sin­gle language to be sup­ported or several languages in which case you can switch from one lan­guage to an­other within the document as required.

The package `ba­bel` uses configuration files that pro­vide the de­tail of what has to be done for each lan­guage.

## Monolingual support

In the following example, only US English is selected.

```latex
%% Use US English
\usepackage[english]{babel}
```

## Multi-lingual support

In the following example, German and US English are selected.

```latex
%% Use German and US English
\usepackage[ngerman,english]{babel}
```

More details on the `babel` package are available [here](http://vesta.informatik.rwth-aachen.de/ftp/pub/mirror/ctan/macros/latex/required/babel/base/babel.pdf). 

[Next: Defining page size, margins and layout](/latex/setting-page-layout.html)
