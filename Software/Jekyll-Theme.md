---
layout: default
title: Jekyll-Theme
has_children: false
permalink: software/jekyll-theme
parent: Software
---

# Jekyll-Theme

## What is Jekyll?

Jekyll is the software that is used by (among others) GitHub Pages to compile Markdown files into "real" webpages.
The themes decide what the end result looks like, just like when you choose a theme (e.g. dark/light) on your smartphone.

## Install on Ubuntu

I took this information from [here](https://jekyllrb.com/docs/installation/ubuntu/), and changed it for zsh (see below).

For bash:

```bash
sudo apt-get install ruby-full build-essential zlib1g-dev

echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

gem install jekyll bundler
```

For zsh:

```zsh
sudo apt-get install ruby-full build-essential zlib1g-dev

echo '# Install Ruby Gems to ~/gems' >> ~/.zshrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.zshrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc

gem install jekyll bundler
```

After that, you can run

```zsh
gem install bundler jekyll
jekyll new my-awesome-site
cd my-awesome-site
bundle exec jekyll serve
```

to create a new site and run it locally.

To later build your site statically, you can just run `jekyll build` (or `jekyll b`).
The built result is stored in `_site`.

## Requirements for a theme

So, my requirements are:

- Look kind of modern (doesn't need to be too fancy, but a 2005 look is not what I'm looking for)
- Have a sidebar for easier navigation
- Text should not be too wide, it should better have a smaller design in the center of the page to make reading easier

## Themes I took a look at

I also looked at many more Themes, but they were so much out of scope <ins>for my purpose</ins>(!) that I didn't even care writing my opinion about it.

### [Minimal Mistakes](https://jekyllthemes.io/theme/minimal-mistakes)

Looks nice but not the kind of Sidebar I'm looking for (I think, maybe I overlooked something).

### [Agus Makmun](https://jekyllthemes.io/theme/agusmakmun-github-io)

Looks interesting, not as modern (I worry about the scaling on mobile devices).
Might be the one.

### [Vonge](https://jekyllthemes.io/theme/vonge)

I literally opened this like three times when going through the library because it looks good, only thing it misses is a sidebar though.
I'm not sure how I could replace this.

### [Contrast](https://jekyllthemes.io/theme/contrast)

Nice one, doesn't show a sidebar here, but on the bottom is a picture where it has a sidebar.

### [Simple](https://jekyllthemes.io/theme/jekyll-simple)

As the title says, its simple.
Also contains a sidebar, so this might be something if there are no other Themes that fit.

### [Just The Docs](https://jekyllthemes.io/theme/just-the-docs)

This might be it.
The focus is more on documentation, but I think this fits the purpose of this page better than Blog or Portfolio themes.

## My decision

In the end, the purpose this site has is mostly documenting stuff, for myself but I'm also happy to help other people with this, which is why I'm publishing it.
This probably the reason why the [Just the docs](#just-the-docshttpsjekyllthemesiothemejust-the-docs) Theme fits my purpose the best.

As a short side-note, GitHub Pages requires this theme to be set as remote-theme in the `_config.yml`, while the local jekyll environment requires (also or only?) the `theme:` variable (e.g. for local preview).
Unfortunately, for some reason GitHub Pages can't find this theme while building the site, and crashes with an error.
For now, I have this variable commented out on GitHub, and not commented out locally.
