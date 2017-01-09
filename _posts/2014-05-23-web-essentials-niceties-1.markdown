---
layout: post
title: "Auto-updating CSS vendor prefixes with Web Essentials"
date: 2014-05-23 20:20:17 +0100
comments: true
categories: CSS
published: false
---

Anyone who's anyone who uses Visual Studio for web development uses Web Essentials. You could, er, say it was _essential_ but I'm above making cheap jokes like that ;)

It offers so much functionality that sooner or later you'll stumble across something you hadn't noticed before. It'll just be a little something, but it'll make you smile, and then you'll want to use it all the time. One such feature I stumbled across this week is the auto-updating of vendor prefixes in CSS.

If you pick anyCSS3 feature at random, the chances you'll need to add some vendor prefixes to make sure it works cross-browser:

    nav {
	    -moz-border-radius: 4px;
		-ms-border-radius: 4px;
		-o-border-radius: 4px;
		-webkit-border-radius: 4px;
		border-radius: 4px;
		...
	}

Every time your designer wants you to tweak the `border-radius` you've got 4 extra CSS rules to update too. And that's the last thing you want to be doing when you could be reading Hacker News. Well, fret no longer, as Web Essentials has you covered:

[!img]

As long as you edit the _real, non-vendor prefixed_ CSS rule, all the others will update themselves automagically.
