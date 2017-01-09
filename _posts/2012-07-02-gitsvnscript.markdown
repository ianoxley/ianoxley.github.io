---
layout: post
title: "gitsvnscript"
date: 2012-07-02 21:32
comments: true
categories: [javascript,git]
---

Since I've been using Git, git-svn has become my preferred way of using Subversion. To make that `git svn clone` command a bit easier for svn projects hosted on Google Code, I've created a Greasemonkey script / user script that:

1. Finds the `svn checkout` command on the source checkout page e.g. [https://code.google.com/p/bbc-radio-scrobbler/source/checkout](https://code.google.com/p/bbc-radio-scrobbler/source/checkout)
2. Appends the equivalent `git svn clone` command, using the standard layout option `-s`.

The source code is available on [GitHub](https://github.com/ianoxley/gitsvnscript),
and you can install it directly from this link:
[https://github.com/ianoxley/gitsvnscript/raw/master/gitsvn.user.js](https://github.com/ianoxley/gitsvnscript/raw/master/gitsvn.user.js) 
