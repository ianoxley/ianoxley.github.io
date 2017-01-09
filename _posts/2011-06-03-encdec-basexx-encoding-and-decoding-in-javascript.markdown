---
date: '2011-06-03 23:13:08'
layout: post
slug: encdec-basexx-encoding-and-decoding-in-javascript
status: publish
title: encdec - BaseXX Encoding and Decoding in JavaScript
wordpress_id: '481'
categories:
- javascript
tags:
- github
- javascript
---

Recently, while hacking around with some Python code I came up with a [Gist for base58 encoding and decoding](https://gist.github.com/865912). Now, just for fun, I thought it would be a good idea / exercise to port this over to JavaScript. This gave rise to [**encdec** - a small base encoding / decoding library](https://github.com/ianoxley/encdec). 

By default if uses base58 encoding, but it does let you pass it your own base alphabet allowing you to do base16, base32 or base-whatever-you-like encoding.

Please [have a play with it](https://github.com/ianoxley/encdec) and let me know what you think :)
