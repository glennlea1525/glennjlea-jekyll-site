---
layout: article
title: Markdown syntax cheatsheet
description: This is the beginning of a more useful cheatsheet of Markdown tags. It also includes links to online Markdown cheatsheets that I have discovered.
date: '2021-12-15'
categories: documentation
---
# {{ page.title }}

* Do not remove this line (it will not be displayed)
{:toc}

This is a brief but hopefully useful Cheatsheet for Markdown syntax. It isn't comprehensive but has the most frequently used markdown that I use in my docs. It is a work in progress and is added to as I get around to doing it.

## Headers

```markdown
# Header one
## Header two
### Header three
#### Header four
##### Header five
###### Header six
```

## Comments

Text can be commented out using the `<!-- -->` syntax:

```markdown
<!--
This is some text I want commented out for the time being. 
-->
```

## Paragraphs (Body text)

Paragraphs can be added simply by entering some text then putting a blank line between the paragraphs:

```markdown
Lorem ipsum dolor sit amet, consetetur sadipscing elitr.

Lorem ipsum dolor sit amet, consetetur sadipscing.
```

Lorem ipsum dolor sit amet, consetetur sadipscing elitr.

Lorem ipsum dolor sit amet, consetetur sadipscing.

## Font styling

Bold, emphasis and strikethrough are added using:

```markdown
**bolded word**
*emphasized word*
~~strikethrough word~~
```

>**bolded word**
>*emphasized word*
>~~strikethrough word~~

## Inline HTML

Markdown accepts inline HTML including classes and inline styles. The following shows inserting an image using HTML:

```markdown
<img class="post-image" src="path/to/image.pnd" alt=" Alt text" />
```

## Horizontal Rules

An `<hr>` element can be added quickly using:

```markdown
___ (three underscores)
--- (three dashes)
*** (three asterisk)
```

## Links

Links are added using the following syntax:

```markdown
[Description of the link](Path to the link)
```

To add a tooltip to the link use the following syntax:

```markdown
[Description of the link](Path to the line "Tooltip added here")
```

## Images

Images can be added using HTML or markdown. In markdown use the following syntax:

```markdown
![Description of the image](path/to/image.png "Alt text")
```

```markdown
<img class="post-image" src="path/to/image.pnd" alt=" Alt text" />
```

## Blockquote

### Single line blockquote

```markdown
> Lorem ipsum dolor sit amet, consectetur adipiscing elit.
```

> Lorem ipsum dolor sit amet, consectetur adipiscing elit.

### Multi-line blockquote

```markdown
> Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Lorem ipsum dolor sit amet, consectetur adipiscing elit.
```

> Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Lorem ipsum dolor sit amet, consectetur adipiscing elit.

## Tables

Tables can be inserted using HTML or Markdown. In Markdown, use the following syntax:

```markdown
| Heading  | Heading |
|  ---     |   ----  |
| Cell     | Cell    |
```

| Heading  | Heading |
|  ---     |   ----  |
| Cell     | Cell    |

## List of items

### Unordered Lists (Nested)

You can use `*`, `-` or `+` as valid bullet symbols.

```markdown
- List item one
  - List item one
  - List item two
  - List item three
  - List item four
- List item two
- List item three
- List item four
```

- List item one
  - List item one
  - List item two
  - List item three
  - List item four
- List item two
- List item three
- List item four

### Ordered List (Nested)

Markdown renders an ordered list if the item begins with a number followed by a period and space. You can use `1. ` and it will render into an order list. 

```markdown
1. List item one
   1. List item one
   1. List item two
   1. List item three
   1. List item four
1. List item two
1. List item three
1. List item four
```

1. List item one
1. List item one
   1. List item one
   1. List item two
   1. List item three
   1. List item four
1. List item two
1. List item three
1. List item four

## Code

### Inline Code

Snippets of code within a sentence can be rendered using back ticks.

```markdown
This is a sentence that contains `code` inside the sentence.
```

This is a sentence that contains `code` inside the sentence.

### Code snippets with syntax highlighting

Markdown flavours support many language snippets. A code snippet is added using three back ticks (```) followed by the language renderer, such as Ruby, Python, Bash, Markdown and ends with three back ticks.

```python
   # Print Hello World
   print("Hello World")
```

## More information

- [Official Jekyll Markdown page](https://jekyllrb.com/docs/configuration/markdown/)

- [Basic Syntax form the Markdown Guide](https://www.markdownguide.org/basic-syntax/)

- [How to Style Images with Markdown](https://www.xaprb.com/blog/how-to-style-images-with-markdown/)
