---
layout: post
title: "Toggling JavaScript Indentation in Emacs"
date: 2013-11-22 20:29
comments: true
categories: [Emacs, Elisp]
---

I _think_ I've written some elisp that is in danger of actually being useful. Its used to toggle the number of spaces used to indent JavaScript code betwee 2 and 4. Why? Well, when I clone or fork JavaScript projects on GitHub, some use 2 spaces for tabs whereas others use 4. Using this function I can toggle between the two settings with ease.

Here's the code:


	(defun js2-toggle-indent ()
	  (interactive)
	  (setq js-indent-level (if (= js-indent-level 2) 4 2))
	  (setq js2-indent-level (if (= js-indent-level 2) 4 2))
	  (setq js2-basic-offset (if (= js-indent-level 2) 4 2))
	  (message "js-indent-level, js2-indent-level, and js2-basic-offset set to %d"
			   js2-basic-offset))

Because I'm using [js2-mode](http://www.emacswiki.org/emacs/Js2Mode) I'm toggling `js2-indent-level` and `js2-basic-offset` in addition to `js-indent-level`.

I _had_ tried implementing this by putting `js-indent-level`, `js2-indent-level`, and `js2-basic-offset` in a list and using `mapc` to modify them. I was trying something like this:

	(mapc (lambda (elem)
			(setq elem (if (= (symbol-value elem) 2) 4 2)))
		  '(js-indent-level js2-indent-level js2-basic-offset))

But, as far as I could tell, elisp's [dynamic scoping](https://www.gnu.org/software/emacs/manual/html_node/elisp/Dynamic-Binding.html) of variables meant this only modified each item in the scope of the lambda function I passed to `mapc` e.g. outside the scope of this function `js2-indent-level` remained unchanged. At least I _think_ that is what was happening. If you know different, please let me know.
