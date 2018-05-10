---
layout: post
title: Adventures in Spacemacs
date: 2018-05-10
tags:
  -vim
  -emacs
  -spacemacs
---

Recently I decided to give [Spacemacs](http://spacemacs.org/) a try. If you've not heard of Spacemacs, it's a combination of Emacs and Vim with tons of ergonomical key bindings.

Things I really like about it so far include:

1. That any Git repo automatically becomes a project
2. The recent projects list / project switcher
3. Fuzzy finding logic when opening a file in a project (I'm used to using fzf with Vim, so this has so far been a seemless replacement)
4. The ease with which it kind of sets itself up for you when you open a file of a particular type (I opened a HTML file for the first time it offered to install the HTML layer which comes with [emmet-mode and loads of useful key bindings](https://github.com/syl20bnr/spacemacs/tree/master/layers/%2Blang/html))
5. Org mode
6. Key binding discovery :heart:
![Spacemacs key binding discovery](/assets/img/spacemacs_key_binding_discovery.png)

I've come across a few snags though:

1. Org mode wouldn't quite work out of the box. I had to exclude the [org-projectile](https://github.com/syl20bnr/spacemacs/issues/9374#issuecomment-336688513) package, and ensure I was [_not_ using the built-in org mode](https://github.com/syl20bnr/spacemacs/issues/8074#issuecomment-280253777).
2. Keyboard shortcuts when using the shell layer are all kinds of messed up. I suspect it's some sort of conflict between the Emacs shell commands and the Evil layer / commands and need to spend some time figuring out what's what.

Time will tell whether I stick with Spacemacs, or revert back to Vim. So far though, so good.
