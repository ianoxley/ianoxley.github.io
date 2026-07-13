---
layout: post
title: Configure jk to exit insert mode in Doom Emacs 
date: 2026-07-13
tags:
  -emacs
  -doom
---
For years I configured Vim to exit insert mode via pressing `jk` in quick succession.

How do you do this in Doom Emacs? By adding the following snippet to your `config.el` file:

```
(after! evil
  (setopt evil-escape-key-sequence "jk"))
```

By using Doom's `after!` macro you ensure your change to the escape key sequence doesn't get overwritten by Doom's default configuration.

