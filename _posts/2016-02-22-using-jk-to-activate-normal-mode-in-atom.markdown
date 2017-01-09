---
layout: post
title: "Using jk to activate normal mode in Atom"
date: 2016-02-22 21:01:31 +0000
comments: true
categories: atom, vim, note-to-self
description: "How to setup Atom keybindings with vim-mode so you can exit insert
mode by pressing 'j k'"
---

Assuming you've already installed Atom's [vim-mode](https://github.com/atom/vim-mode) package, edit keymap.cson to include the following:

    'atom-text-editor':
      'j k': 'vim-mode:activate-normal-mode'

As per https://github.com/atom/vim-mode/issues/334#issuecomment-124608450
