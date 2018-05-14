---
layout: post
title: "More adventures in Spacemacs"
date: 2018-05-14
tags:
  -spacemacs
---

Following on from [last week's post](http://www.ianoxley.com/blog/2018/05/10/adventures-in-spacemacs) here's a couple of Spacemacs related things I've come across since then.

## Jekyll layer
I write this blog using [Jekyll](https://jekyllrb.com/), so I've added a [Jekyll layer](https://allysonjulian.com/posts/blogging_with_spacemacs_and_jekyll/) to make managing posts a bit easier. You need to add it as a private layer, and it acts as a wrapper around [Hyde](https://github.com/nibrahim/Hyde) with some Spacemacs key bindings.

## dotspacemacs-major-mode-leader-key

Spacemacs comes with a `dotspacemacs-major-mode-leader-key` variable, which defaults to `,`. This acts as a shortcut to access the major mode `SPC m` commands. However, I didn't know about this when I setup Spacemacs and remapped my leader key to `,`. Consequently, when I tried to schedule an item in org mode I couldn't work out why it didn't schedule the item but opened a new email with my whole org file in it as HTML :thinking:

To get around this I've updated my `.spacemacs` file and set `dotspacemacs-major-mode-leader-key nil` in `dotspacemacs/init`.

