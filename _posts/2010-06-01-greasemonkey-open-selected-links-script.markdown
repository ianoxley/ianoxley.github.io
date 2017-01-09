---
date: '2010-06-01 22:02:24'
layout: post
slug: greasemonkey-open-selected-links-script
status: publish
title: Greasemonkey Open Selected Links Script
wordpress_id: '378'
categories:
- javascript
tags:
- greasemonkey
- javascript
---

I hadn't done any monkeying around with [Greasemonkey](https://addons.mozilla.org/en-US/firefox/addon/748/) for a while until the other day when I came up with this script: [http://github.com/ianoxley/open-selected-links](http://github.com/ianoxley/open-selected-links)

Any links that are present in the selected text will be opened on the `mouseup` event, except for the **Cached** and **Similar** links you get in Google search results.

If you've got and suggestions for improvements, let me know in the comments :)

### UPDATE

The script has been updated so that you now have to press the `Ctrl` or `Cmd` key while selecting the text, in the same way that you would `Ctrl / Cmd + click` to open a link in a new tab.
