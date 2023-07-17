---
layout: default
title: RSS Reader
has_children: false
permalink: software/rss
parent: Software
math: katex
---

# RSS Reader

I'm looking for a self-hosted RSS Reader, with the following requirements:

- Self-Hosted: obviously, but it must run on a server and provide either a Webinterface or a client for multiple platforms (Win+Mac, preferably also Linux and Android). A client like Thunderbird doesn't work for me as these clients
  - a) usually don't sync between machines and
  - b) do not run 24/7, so I might miss some stuff when I'm offline for lets say 2-3 days.
- Modern UI: I simply don't enjoy using some ancient UI, Terminal is also not an option in this case as I this is mainly for reading news from news websites
- Configurability: to be exact, this is one of the reasons I don't want some third-party service but want it self-hosted
  - Custom Intervals: For some things I want only a few minutes between updates (e.g. newsfeeds or feeds of outages), some things (like updates for certain software) are okay if they only update once a day
  - When to delete articles
- Running in a docker container: Well, I could build one myself or whatever... but I don't want to spend big amounts of time to fix weird bugs, I want something that just works. I have other stuff to do than fixing some RSS Reader.

## Options

There are already some articles about different options, but here is the list of options, I took a look at.

### [Tiny Tiny RSS](https://tt-rss.org/)

### [FreshRSS](https://github.com/FreshRSS/FreshRSS)

- Looks kind of crappy, I really don't like the design they use (especially when looking at the large blue button thats already shown on their website)
- As far as I saw, it doesn't have a three-column reading option (which is a must for me), although I might have overlooked it

### [yarr (yet another rss reader)](https://github.com/nkanaev/yarr)

- Not a fan of the installation process, which is downloading a binary and storing it somewhere (I pretty much want a docker container that just works for stuff like this)

### [Miniflux](https://miniflux.app/)

- No to this UI.

### [rss2email](https://github.com/rss2email/rss2email)

Sends Articles from RSS Feeds via Mail.
Might be something like an emergency solution, but I favor pretty much everything over this.

### [feedpushr](https://github.com/ncarlier/feedpushr)

I'm not sure what my problem was with this one, but it was probably that they don't really have screenshots and also not a demo, so I was too lazy to install it myself just to test it.
But since I found something else with which I'm pretty happy, I didn't care anymore.

### [JARR](https://www.jarr.info/)

I already trashed a system with python venvs, so I don't want to rely on this to install an RSS Aggregator.

### Not an option

Too old interface, I just don't like it

- [Temboz](https://github.com/fazalmajid/temboz)
- [Stringer](https://github.com/stringer-rss/stringer)
- [Sismics Reader](https://www.sismics.com/reader/#!/home)

Don't like the view, I'd rather have a reader where you can open each element like an email.

- [RSSMonster](https://github.com/pietheinstrengholt/rssmonster)
- [selfoss](https://selfoss.aditu.de/)
- [Newspipe](https://git.sr.ht/~cedric/newspipe)
- [newsdash](https://github.com/buzz/newsdash)
- [CommaFeed](https://www.commafeed.com/#/welcome)

## Final words

I've now decided for tt-rss, which I'm now using for a few weeks.
I really like it, since it just works nicely.
It syncy everything to the server, its fast and responsive, I can save stuff for later (I'm abusing the star function for this, but I also don't know what else I should use it for so thats not a problem) and it gives me enough customization options like custom update intervals per feed.

Only problem currently is that it logs me out every like two days, which is a bit annoying.
Maybe that's just an option which I could change, but I haven't investigated yet.
