---
layout: post
title: "node-encdec"
date: 2012-09-03 19:37
categories: [javascript, node]
---

A while back I wrote a [gist for base58 encoding / decoding in Python](https://gist.github.com/865912), then [ported it to JavaScript](https://github.com/ianoxley/encdec). The other day I thought it would be good fun to convert the JavaScript version to a npm module so it can run on Node.js, and here's the result: [https://npmjs.org/package/encdec](https://npmjs.org/package/encdec)

It's essentially the same as the original version. The only real difference is the unit tests are now in [nodeunit](https://github.com/caolan/nodeunit) instead of [QUnit](http://docs.jquery.com/QUnit).

You can install node-encdec via npm:

    npm install node-encdec
	  
    # or to install globally
	  
	  npm install -g node-encdec
