---
date: '2010-12-10 21:07:38'
layout: post
slug: gmail-toolbar-chrome-greasemonkey-script
status: publish
title: GMail Toolbar Chrome Greasemonkey Script
wordpress_id: '451'
categories:
- web
tags:
- chrome
- greasemonkey
- javascript
---
### Update
This no longer works with the new GMail UI

I quite like the toolbar at the top of GMail. You know, the one with links to Google Calendar, Google Reader, Google Docs, et al. But I'm not that keen on having to scroll right back to the top of the page each time I need access to it. So, I created a simple Greasemonkey script for Google Chrome to apply fixed positioning to the toolbar. That way it always stays at the top of your screen :)

(Firefox users: I did create a [user stylesheet that achieves the same effect](https://github.com/ianoxley/userContent)
 recently. However, that relies on the `@-moz-document domain(mail.google.com)` to restrict the CSS to GMail and Google seems to send different HTML to Firefox than it sends to Chrome).

You can fork a copy of the script from GitHub: [https://github.com/ianoxley/gmailtoolbar](https://github.com/ianoxley/gmailtoolbar)

Or alternatively download it from here: [gmailtoolbar.user.js](/greasemonkey/gmailtoolbar.user.js)
