---
layout: post
title: "Getting the solarized8 theme working in Vim in tmux"
date: 2019-09-10
tags:
  -vim
  -tmux
  -iterm
---

My current theme of choice in Vim is
[solarized8](https://github.com/lifepillar/vim-solarized8), which requires true
colors support in your terminal. It works perfectly when running Vim inside of
iTerm, but it wasn't working quite as well in Vim [inside
tmux](https://camo.githubusercontent.com/09751398c97d1a3907c45d45072c9a40010d3a8c/68747470733a2f2f7261772e6769746875622e636f6d2f6c69666570696c6c61722f5265736f75726365732f6d61737465722f736f6c6172697a6564382f736f6c6172697a6564385f6461726b5f3235362e706e67).

Lots of advice online suggests either making sure you launch tmux using `tmux
-2`, or adding `set -g default-terminal "screen-256color"` to your
`~/.tmux.conf` file. Neither of these fixes worked for me, although YMMV.

What _did_ fix things for me was adding terminal overrides to `~/.tmux.conf`
like so:

```
set -ga terminal-overrides ",*256col*:Tc"
```

Huge thanks to [rineth](https://github.com/rinetd) for their [helpful
post](https://github.com/tmux/tmux/issues/1246).
