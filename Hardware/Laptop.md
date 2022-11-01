---
layout: default
title: Laptop
has_children: false
nav_order: 2
permalink: hardware/laptop
parent: Hardware
---

# Laptop

As my laptop, I use a 15 inch MacBook Pro 2018.

## Using a mouse

I really like the trackpad, but sometimes a mouse might be helpful.
As the "mouse" acceleration is an important part for the usability of the trackpad, I do not want to disable it globally, but on the other hand, who wants to use mouse acceleration with a real mouse?

macOS out of the box does not offer an option to disable mouse acceleration for one input device, but keep it enabled for another.
There is a program that I found, which fixes exactly that: <https://linearmouse.org/>.
It can be installed using homebrew by running:

```zsh
brew install --cask linearmouse
```

It can not only fix the mouse acceleration issue, but also scroll acceleration and scroll directions.
