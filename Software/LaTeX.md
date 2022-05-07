---
layout: default
title: LaTeX
has_children: false
permalink: software/latex
parent: Software
math: katex
---

# LaTeX

## What is LaTeX?

As a very basic description, LaTeX is a script language that can be compiled into documents (e.g. PDFs or older DVIs).
It is used quite a lot in science, as it is more comfortable to work with than [WYSIWYG](https://en.wikipedia.org/wiki/WYSIWYG) text editors like Word, especially for writing mathematical things.

## How do I use it?

There are several ways, and I'm only going to describe the way I use it.
This is the way I find most useful and best to work with, with my experience of about two years writing a lot of stuff (e.g. exercises for my studies) in LaTeX.

I use [VS Code](https://code.visualstudio.com/), with the [LaTeX Utilities](https://marketplace.visualstudio.com/items?itemName=tecosaur.latex-utilities) and the [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) plugins.
These add language support aswell as some convenience features, like a table of mathematical symbols so you don't always have to google them if you don't remember their name ([Detexify](https://detexify.kirelabs.org/classify.html) will also help here).
Also, you want to install the [Remote - SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh) Plugin.

In the background, I have a virtual machine running, which runs some sort of Linux (for me its Ubuntu), an OpenSSH server (so I can connect to it using VS Code and the Remote - SSH Plugin) and the texlive distribution (installed using `sudo apt install texlive-full`).
This combination lets you work on your main machine as you would on linux, including the faster compile times which I also describe [later on this page](#compile-on-linux).
Running your VM using a NATted network interface should be enough, as this gives your VM full internet access (e.g. for updates and access to GitHub), and also allows your machine to connect into the VM.
However, you should be at least a little bit familiar with Linux.

### A first very basic document

\- Todo -

## Tips and tricks

### Compile on Linux

So, this is actually the most important thing in my opinion.
Compiling LaTeX on Linux gained me 3-7 times faster compile times (depending on the content of the document) compared to Windows and macOS, even though I'm running this inside a virtual machine on the same hardware.
Yes, you heard it right.
On my normal desktop that I use for my daily work, I'm running a Ubuntu virtual machine, which I connect to using the [Remote - SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh) plugin of VS Code [as described above](#how-do-i-use-it).

### Own commands for math symbols like $$\N$$

Usually, mathematical signs like "$$\N$$" are written something like `$\mathbb{N}$`.
This is obviously too long if you're writing that very often, so there is something nice you can do:

```latex
\newcommand{\N}{\ensuremath{\mathbb{N}}}
```

This allows you to just write `\N` instead of the aforementioned `$\mathbb{N}$`.

The `\ensuremath{}` even makes sure that math mode is enabled, so you don't need to enable it manually every time and you don't have to think if you're maybe turning it off by accident etc.
I discovered this way too late, but since then, I always encluded this.

So what I've ended up with is something like this:

```latex
\newcommand{\e}{\ensuremath{\varepsilon}} % epsilon sign
\newcommand{\F}{\ensuremath{\mathbb{F}}} % finite sets
\newcommand{\PR}{\ensuremath{\mathbb{P}}} % prime numbers
\newcommand{\N}{\ensuremath{\mathbb{N}}} % natural numbers
\newcommand{\Z}{\ensuremath{\mathbb{Z}}} % integers
\newcommand{\Q}{\ensuremath{\mathbb{Q}}} % rational numbers
\newcommand{\R}{\ensuremath{\mathbb{R}}} % real numbers
\newcommand{\Cn}{\ensuremath{\mathbb{C}}} % complex numbers
```

### Create yourself a template

If you work with LaTeX a lot and on many different documents (as mentioned before, I did a lot of exercises for my studies in LaTeX), you want to create your own template.
For my part, I added convenience features so that I just have to fill in the names of the people who worked on it, the subject and the number of the exercise sheet.
If I'm not working on an exercise sheet, I can simply use one toggle to switch to a layout which allows me to write longer documents.
