---
date: '2009-04-24 23:04:19'
layout: post
slug: greasemonkey-script-to-bypass-the-add-to-google-homepage-or-google-reader-page
status: publish
title: Greasemonkey Script to Bypass the Add to Google Homepage or Google Reader page
wordpress_id: '76'
categories:
- javascript
tags:
- javascript greasemonkey
---

I have just created a quick Greasemonkey script to bypass the Add to Google page and add feeds straight to Google Reader.

The Add to Google page offers you the choice of adding a feed to your Google homepage or Google Reader and, seeing as I don't really use my iGoogle page, adding them straight to Google Reader makes more sense and elimates that extra click.

Now, I know Google make a Subscribe... bookmarklet available to "subscribe as you surf" (via Manage Subscriptions -> Goodies in Google Reader). But since I have been using the [NoScript Firefox extension](https://addons.mozilla.org/en-US/firefox/addon/722) this bookmarklet often does not work for me, as the site I am on typically will not be on my NoScript whitelist.

So instead of using the bookmarklet I started subscribing to feeds directly through Firefox:
	
  1. Click the feed icon in the address bar
  2. Select Google on the Firefox subscribe page and click the button
  3. Select Add to Reader on the Add to Google page

After a while though, clicking Add to Reader everytime was causing some friction. So I came up with my Straight to Reader Greasemonkey script: the Add to Google page loads before you are redirected straight to Google Reader and subscribed to the feed.

If you want to give it a try you can install it here: [straighttoreader.user.js](http://www.strongasanox.co.uk/greasemonkey/straighttoreader.user.js).

Alternatively you can view the script and [install it from userscripts.org](http://userscripts.org/scripts/show/47474).

**UPDATE**: I have fixed a bug in the original version so that, if you are not currently logged in to your Google Account, you still get forwarded on to the Add to Reader page (via the Google Account sign in page).
