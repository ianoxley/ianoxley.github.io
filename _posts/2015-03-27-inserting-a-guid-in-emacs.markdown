---
layout: post
title: "Inserting a UUID in Emacs"
date: 2015-03-27 22:20:51 +0000
comments: true
categories: emacs
description: A little function for Emacs to insert a UUID at point in the current buffer
---

Although there's no built-in support for generating a UUID in Emacs, a
quick search on Google yields plenty of solutions to choose from. I
chose Nic Ferrier's [emacs-uuid](https://github.com/nicferrier/emacs-uuid), and
wrote my own little function to insert a UUID at point in the current buffer.

I put `emacs-uuid` on my `load-path`, then added the following function
to my `.emacs` file:

	(defun uuid-insert()
	  (interactive)
	  (require 'uuid)
	  (insert (upcase (uuid-string))))
	  
I then bound this to `C-c C-'` so I can insert a UUID without moving my fingers too much:

	(global-set-key (kbd "C-c C-'") 'uuid-insert)
