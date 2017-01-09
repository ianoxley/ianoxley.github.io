---
layout: post
title: Remap Capslock in Windows with AutoHotkey
date: 2012-07-31
comments: true
categories: [hacks]
---

Probably the easiest way to remap the Capslock key in Windows is to use [AutoHotkey](http://www.autohotkey.com/). I have an AutoHotkey script set to run when my machine starts up that remaps Capslock to Escape. All it contains is this:

  Capslock::Esc

If you want to remap Capslock to Ctrl instead, just replace `Esc` with `Ctrl`.

No registry hacking required.

Further Reading
---------------

[Map caps lock to escape in Windows - Autohotkey](http://vim.wikia.com/wiki/VimTip75#AutoHotkey)

