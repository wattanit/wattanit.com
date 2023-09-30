---
title: "Introduction to Professional Text Editors"
pubDatetime: 2016-09-05T09:36:15+07:00
tags:
  - vim
  - editors
  - programming
description: Text editor is the most important tool for a programmer. Period. It is pretty much like a sword in the hand of a warrior. There can be many kinds of different swords, each with its own pros and cons, but at the end of the day it has to be the one that is right to its user.
---

_2020 remark:
This article was first published in 2016 under the name [Vim resources (and other text editors)](https://rorasa.wordpress.com/2016/09/05/vim-resources-and-other-text-editors/)._

_It's been 4 years since this article was first published yet the landscape of text editing remains the same, everything follows still valid._

Text editor is the most important tool for a programmer. Period. It is pretty much like a sword in the hand of a warrior. There can be many kinds of different swords, each with its own pros and cons, but at the end of the day it has to be the one that is right to its user.

I’ve used several text editors over the years, most of which are quite famous. To cut to the chase, in the end I’m switching to Vim and would like to share resources for those who would like to swtich too.

But before we go there, let’s review other text editors out there.

## Stock text editors

- WIndows Notepad : No need for explaination. Everybody knows and ~~hate~~ love this little editor from Microsoft. It can edit text. Nothing else.
- MacOS TextEdit : This one is more like a combined text editor/ rich-text editor. It can edit text alright but probably more suitable for some nice piece of writing instead of programming.
- Gedit : If you use a linux with Gnome desktop, you will have this text editor comes prebundled with it. It is a very decent text editor in its own right, with many features you would expects from a professional text editor such as syntax-highlighting. If you have this one then you probably don’t need anything else.

## Professional text editors

Every editor from here on has all the features you would expect from a professional-grade text editor such as syntax-highlight, code auto-completion, recordable macro, plug-ins, built-in file browser, version control integration, command line integration etc.

- [Notepad++](https://notepad-plus-plus.org/download/v6.9.2.html) : A very powerful, very lightweight text editor for Windows. It is very popular and feature-packed, though its look-and-feel is a bit retro.
- [TextWranger](http://www.barebones.com/products/textwrangler/) : A good text editor for MacOS. I’ve been using this for quite sometine until I switch to Atom that has greater customisation.
- [Sublime Text](https://www.sublimetext.com/) : A gold standard for modern text editor. It’s feature-rich and it’s very beautiful. It is a new generation of software, where distraction-free interface is favoured over a complex mess of icons and toolbars found in older generation. Sublime Text has many killer features that I like such as the multiple selection and the all-purpose command palette. Its price is also a killer at $70 a copy, which is the reason this list still continues on.
- [Atom.io](https://atom.io/) : A text editor developed by Github to be extremely hackable. Every aspect of Atom is customisable as the whole software is built on the web technology (Javascript and CSS) that runs on a Chrome frame. Atom was my default text editor for quite a few years. It offers a set of features similar to that of Sublime Text without any cost. The look-and-feel is inspired by Sublime Text and is themeable. Atom is very easy to use, has a very smart command palette, has a comprehensive list of plug-ins, and is very modern. The only real isssue with Atom is the fact that it runs on a Chrome frame, which requires a hugh amount of resources. If you use Google Chrome you will know the feeling.
- [Visual Studio Code](https://code.visualstudio.com/) : VS Code is a text editor from Microsoft designed to rival Sublime Text and Atom. It has all the features of Sublime Text and Atom, including the plug-ins and command palette. The look-and-feel is also very modern. Despite its name, VS Code is not a part of Visual Studio suite and is available free of charge. The last time I used VS Code has considerably less plug-ins than Atom. On the plus side, it opens up faster.

## Vim and Emacs

All the above professional text editors are solid enough to be your text editor of choice. They’re modern, feature-rich, and extensible. So what is the problem?

The problem is the workflow. While these editors are good, they are still needed to open up as another program. Sometimes it’s better to stay inside your command-line terminal rather than to switch to another window. The other problem is that they are designed to use with modern mouse and keyboard setting. Surprisingly, switching from keyboard to mouse frequently can be quite frustating. Not to mention that in some situation you cannot use GUI-based text editor at all (SSH session is a popular case).

Because of this many people have switched back to the eldest text editors around: [Vim](http://www.vim.org/) and [Emacs](https://www.gnu.org/software/emacs/) (and for some, [Nano](https://www.nano-editor.org/)). They operate purely in text-mode which requires no mouse interaction. Their learning curves are quite steep compared to modern editors but experience users can use them so efficiently that put modern editors to shame. It is interesting to note that [Emacs and Vi have history of being a rival](https://en.wikipedia.org/wiki/Editor_war), both with a large group of users claiming their editor of choice to be better than the other. I have only little experience with Emacs myself but I can say that its extensibility is far beyond a text editor. (Emacs’ Org-mode alone can acts as a todo-list, outliner, note-taker, project management, all in one package, for example.)

As of late I’ve been switching to Vim as my default text editor for everything. Even though I am quite familiar with it for many years, I’ve been put off by the need to memorise all of its command keys. For those of you that do know about Vim, it is an improved version of Vi editor—a command-line only text editor that has been around forever. Vi and Vim are labelled as a notoriously hard program to quit (mainly because no novice can correctly quess how to quit it using :q! command). However, once I started to accomodate a few essential commands, the rest followed surprisingly easily. The best part that I like about Vim, which is also the main reason I switched from Atom, is that it is extremely lightweight. You can open and close a Vim session nearly instantaneously, with the speed limits by the speed of your own typing. This lightning fast and feather-light footprint stunned me (who used such a heavyweight system like Atom—please remember that it runs on the Chrome frame). I must admit that I missed the convenience and beauty of Atom at first, but after I started to customise my Vim, I must say I never look back ever again. With the right customisation, Vim can be as beautiful and convenient as any modern browser.

Vim is one of those software that grows along with its user. New users start with a fresh Vim. Mature users however grow their own Vim to be completely different monsters.
