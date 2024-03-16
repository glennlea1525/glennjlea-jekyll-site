---
layout: article
title: GitBook or MKDocs for product documentation?
description: In the past two years I learned two different, but related, tools for creating technical documentation. The first was GitBook, while the second was MKDocs (Material for MKDocs). In this post I provide my analysis of using both tools and which of the two I consider a better choice. 
categories: documentation
date: '2022-01-01'
---

# {{ page.title }}

In the past two years I worked with two different tools for producing technical documentation. They both use Markdown but approach writing content entirely differently. I used **[GitBook](https://www.gitbook.com/)** for over a year during 2091 and 2020. I used **MKDocs** - specifically **[Material for MKDocs](https://squidfunk.github.io/mkdocs-material/)** - following that from 2020 to today. Having previously worked with tools such as Flare, [Wagtail](https://github.com/wagtail), Help & Manual, Adobe FrameMaker, I was glad to write documentation using tools that allow me to use Markdown. At this point, I have used both sufficiently to make an intelligent analysis of GitBook and MKDocs and form some conclusions as to which is the better choice, at least for me.

Both GitBook and MKDocs were chosen not by me but by the engineers and product managers of the respective companies for which I produced documentation. Both of these tools would automatically make them a good choice because (1) these companies wanted to use them and (2) it is always good to be on the side of the engineers and project managers on any project. Sure, I sometimes have had an opportunity to advise which tool to use - and I have done that many times - but I was glad to just jump in to an existing tool set and start swimming.

## What is GitBook?

GitBook used to be an [open-source tool](https://github.com/GitbookIO/gitbook) for creating documentation but a few years ago it became proprietary. This meant I was dependent on the features the GitBook company allowed me to use. Second, it is hosted on a GitBook server not on a local repository so if it was down, so was our documentation.

<figure><img class="img" src="{{ baseurl }}/assets/img/blog/gitbook.png" alt="Gitbook" /></figure>
<figurecaption>GitBook example project</figurecaption>

On the other hand, it is easy to use - if you were happy with the features they provided, which I sometimes was not. It is very simple. First, I signed in to [app.gitbook.com](https://app.gitbook.com/) then I chosed the type of project - Docs. GitBook then built a template for me and then I started writing my topics. To be fair, since I last worked with GitBook they have significantly upgraded their offerings and features. So, it seems they have listened to some of the complaints of customers. But the workflow hasn't changed since I used it and that is what I am most interested in here. 

### Creating topics with GitBook

GitBook does have some useful features such as adding new paragraphs just by hitting **Enter** after an existing paragraph. That's a typical Markdown behaviour. Once I add a paragraph, I you can choose from a set of options to format the paragraph into a heading, list, hint, quote, code block or just keep it as a paragraph. Additionally, I can insert images, files, URLs, tables, tabs and even API methods using the same method. Clearly GitBook has been hard at work since I last worked with this tool. These tasks were more difficult to do when I used it. 

<figure><img class="img" src="{{ baseurl }}/assets/img/blog/gitbook-inline-menu.png" alt="Gitbook" /></figure>
<figurecaption>GitBook inline menu</figurecaption>

Adding captions to inserted images is simple as is embedding YouTube videos, sound files, Codepen and other types of exernal files. When I used it, the options were inserting videos or links to files. So, again they have listed to complaints and expanded their offereings. 

Here is an image inserted with a caption. Notice the pop-up menu that appears over the caption. These sort of pop-up menus are available throughout the topic during edit mode. They allowed me to format words in typical manner such as bold, italics, underlined and so forth. 

<figure><img class="img" src="{{ baseurl }}/assets/img/blog/gitbook-insert-image.png" alt="Gitbook" /></figure>
<figurecaption>Inserting images and captions</figurecaption>

You might notice GitBook has already spell-checked the topic content. This is a basic feature any tool should have. Right-clicking on a misspelled words brings up a menu which I can use to correct the spelling. Basically, this is standard spell checking behaviour.

Many of the tasks in GitBook can be done using keyboard shortcuts, not that I used them that much. But they did make my work a bit easier - when I used them. GitBook now allows importing external documents written in Google Docs, Word or wherever. I also noticed GitBook has listened to its critics and allowed content to be synced with a GitHub repository, something it couldn't do before. 

### So, what do I think about this new and improved GitBook?

Well, its hard to say. I do appreciate its improvements but I am no longer a fan of writing topics within an interface. I like writing topics in something like Atom or Visual Studio Code, basically a tool that allows me to write in Markdown and connect with my repository in GitHub.

But as GitBook does have the word GIT in its name, it must by definition connect with GitHub. Surprisingly, a normal user would not notice this so the name of the product seems a bit archaic or a mismatch. It is probably closer to a tool like Flare or a CMS. And as I fled from Flare some years ago, being roped into another interface like Flare wasn't exactly my cup of tea nor my cup of coffee.

It might be yours though. Yet, unlike Flare it doesn't have a menu on top to format text, import items and so forth. It is all through embedded menus and keyboard shortcuts and lots of mouse clicks to get things done.

### Final score

So, in summary, I would give **GitBook** the following score:

- **5 out of 10 for ease of use**
- **5 out of 10 for writing content**
- **6 out of 10 for project results**

Perhaps the API docs might be its saving grace, although I haven't worked with that part of the tool yet. It is a smart move on the part of GitBook to allow users to integrate API docs into their product documentation using the same tool. To be fair, that aspect of GitBook might be its best selling point.

## What is MKDocs?

MKDocs is a static site generator that, like Jekyll, uses Python and Markdown. Unlike Jekyll which is often used for Blogs, MKDocs is used for product documentation. Similarly with Jekyll, I can develop locally using Visual Source Code or Atom, run a command to generate a site then host the output wherever. MKDocs can be hosted on a GitHub repo for integration into a company documentation site. With MKDocs, many useful themes are available such as [ReadTheDocs](https://docs.readthedocs.io/en/stable/intro/getting-started-with-mkdocs.html) or [Material for MKDocs](https://squidfunk.github.io/mkdocs-material/).

<figure><img class="img" src="{{ baseurl }}/assets/img/blog/mkdocs.png" alt="Gitbook" /></figure>
<figurecaption>MKDocs</figurecaption>

MK in MKDocs, of course, stands for Markdown. I quite like the simplicity of Markdown. It is quite easy to write text without having to worry about layout and design. Well, actually, I have to worry about layout and design but not while writing topics. In fact, in some companies, this aspect of writing docs can be farmed out to the engineering or design teams to keep the look of the docs consistent with corporate standards. This was my experience with it. I had some input into style guides for the docs but the actually layout, colour schemes and so forth were out of my hands. Thankfully I could focus on writing the docs and for that I was quite pleased.

As for processes, using MKDocs is also knowing how to use git commands and GitHub. This was a bit of a learning curve for me but glad to have some day to day experience with it instead of just head-knowledge from my Git books. At the end of each day I uploaded to a corporate repository my work for the day. For major changes I would create a new branch, work on the branch, push it to the repo and run a Pull Request for review and eventual merge into the main repository. It worked quite efficiently.

### Material for MKDocs

Material for MKDocs was developed by Martin Donath (see [github.com/squidfunk](https://github.com/squidfunk)) in Germany. I have had very good experience with this MKDocs theme. As with all MKDocs themes, it requires Python and Pip.

Running `pip install mkdocs-material` installs both MKDocs and the theme. Then running `mkdocs new .` builds a basic structure. Adding a few lines to a basic configuration YAML file `mkdocs.yml` the site is ready to be built using `mkdocs build`. A nice feature is the *previewing as you write* command `mkdocs serve`. The result is a decent basic site ready for customization and content:

<figure><img class="img" src="{{ baseurl }}/assets/img/blog/mkdocs-material-base.png" alt="Gitbook" /></figure>
<figurecaption>Material for MKDocs base</figurecaption>

Of course, the Material for MKDocs theme can be fully customized. In my experience a corporate designer was responsible for colour themes, icons, font use and so forth. Front-end engineers loaded up the `mkdocs.yml` file with these customizations. That was handy. I had input into anything content-related. And as this theme uses Markdown, it was a no-brainer. For example, I could add an admonition using:

```markdown
!!! note "Title of admonition"
    This is a note admonition
```

I could add code blocks quickly using standard Markdown triple ticks followed by language:

```markdown
<3 ticks>py
        python code here
<3 ticks>
```

Basically, if you know Markdown, using Material for MKDocs is a breeze. I am a fan of this theme and MKDocs in general. In my research for this topic, Incidently, I did some research to see of anyone else had compared GitBook with MKDocs. Not to many did but I did find a good review of Material for MKDocs by Steve Martinelli at [www.stevemar.net/five-things-about-mkdocs/](https://www.stevemar.net/five-things-about-mkdocs/). Highly recommended reading.

I liked Steve's his summary of MKDocs:

1. **Good looking interface with a good plugin support**. I have to agree. It's the plugins that make this theme very customizable.

1. **Social media footers function**. I would like this in my own site but this theme makes adding them simple. Always a good selling point.

1. **GitHub Actions integration**. As I have never used this before I can't comment on it, but for those in the know, this must be important, including Steve.

1. **Easy to set up**. I would have put this as the number 1 point. I showed you how easy it was to setup and build a simple site. 

1. **All governed by a single file**. Yep. true. As I mentioned, the `mkdocs.yml` file governs everything in the project. As the engineers set this up I had little to do with it except don't touch it. But it is like a Jekyll site so that makes it a great feature.

I would add that unlke Jekylll, creating a new topic is a real breeze: 

- Adding a new .md file
- Write topic content
- Add the topic to a Navigation (Menu) file
- Running `MKDocs Serve` to preview
- Edit the topic, insert images and so forth
- Push changes to a repo

Simple. Straightforward. Quick. And for technical writers what can be better?

### Final score

So, in summary, I would give **Material for MKDocs** the following score:

- **9 out of 10 for ease of use**
- **9 out of 10 for writing content**
- **8 out of 10 for project results**

Clearly, it is easy to use. As a technical writer, I can quickly write topics. And it creates good looking product documentation.

## Conclusion

**GitBook** has unique advantages. If you like a typical user interface like Word or Flare, I would suggest using GitBook. This, of course, limits customization but GitBook does have many options for embedding different types of content. No need to worry about managing a GitHub repo and it is a WYSIWYG type of tool. It has its uses and user types. But on the downside, it is also proprietary and has a launchpad fee. Writing topics is employing lots of mouse-clicks and right-mouse clicks. And probably the most troublesome, it is an expense for a company.

**Material for MKDocs** is open source. I am sure the maintainer would appreciate some financial support but it is basically a MKDocs theme and freely available. But I think it is a tool with a future. I write so much faster using a text editor like VSC and let a configuration file and navigation file take care of the look and feel of the results. Having now over two years experience with both tools, I can safely say I have enjoyed working with this tool over GitHub.

**Winner: Material for MKDocs.**
