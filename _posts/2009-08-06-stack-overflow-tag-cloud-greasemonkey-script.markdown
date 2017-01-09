---
date: '2009-08-06 21:45:06'
layout: post
slug: stack-overflow-tag-cloud-greasemonkey-script
status: publish
title: Stack Overflow Tag Cloud Greasemonkey Script
wordpress_id: '130'
categories:
- javascript
tags:
- greasemonkey
- stackoverflow
---

[Stack Overflow](http://stackoverflow.com/) is great and I'm a big fan of the site. However, I'm not such a big fan of their tags page:

[![screenshot-tags-stack-overflow](http://www.strongasanox.co.uk/wp-content/uploads/2009/08/screenshot-tags-stack-overflow-300x225.png)](http://www.strongasanox.co.uk/wp-content/uploads/2009/08/screenshot-tags-stack-overflow.png)

Because the tags are ordered solely by popularity and not alphabetically, I find it a bit awkward trying to find a tag I am interested in e.g. if you want to find JavaScript it could be located anywhere in the list.

Admittedly there is a search function to help you find tags but I wanted to be able to scan the list more easily and pick out the tags that interest me most. So, to [scratch my own itch](http://gettingreal.37signals.com/ch02_Whats_Your_Problem.php), I created a [Greasemonkey](https://addons.mozilla.org/firefox/addon/748) script to transform the current tags page into a [tag cloud](http://en.wikipedia.org/wiki/Tag_cloud):

[![screenshot-tags-stack-overflow-greasemonkey](http://www.strongasanox.co.uk/wp-content/uploads/2009/08/screenshot-tags-stack-overflow-greasemonkey-300x225.png)](http://www.strongasanox.co.uk/wp-content/uploads/2009/08/screenshot-tags-stack-overflow-greasemonkey.png)

Because the tags are in alphabetical order with their font size weighted according to popularity, I find it much easier to find tags I am interested in.

Try it out for yourself and see what you think:
	
  * Install [stackoverflow-tag-cloud.user.js](http://www.strongasanox.co.uk/greasemonkey/stackoverflow-tag-cloud.user.js)
  * Install via [userscripts.org](http://userscripts.org/scripts/show/55201)

And if you have any suggestions for improvements, please leave a comment.
