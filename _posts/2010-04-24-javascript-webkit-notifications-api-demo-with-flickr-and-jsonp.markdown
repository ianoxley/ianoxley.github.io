---
date: '2010-04-24 22:12:52'
layout: post
slug: javascript-webkit-notifications-api-demo-with-flickr-and-jsonp
status: publish
title: JavaScript WebKit Notifications API Demo With Flickr and JSONP
wordpress_id: '324'
categories:
- javascript
tags:
- flickr
- html5
- javascript
- jsonp
- webkit notifications api
---

I've been playing around with the JavaScript [Notifications API](http://www.chromium.org/developers/design-documents/desktop-notifications/api-specification) recently - or to be a bit more specific the WebKit Notifications API - and put together [this little demo](http://lab.strongasanox.co.uk/notify.html) using Flickr and JSONP:
	
  1. You search Flickr by entering a tag
  2. The JSONP callback function then displays the first few photos returned using the Notifications API
  3. Each notification is cancelled after 10 seconds (there is no Dismiss button, like there is when you use the API on `localhost`)

You'll need to grant notification permissions first to be able to view the notifications - you should see an info bar like the one below the first time you click on `Search`:

[![WebKit Notifications API requestPermission screenshot](http://ianoxley.com/wp-content/uploads/2010/04/Screenshot-Webkit-Notifications-API-request-permission1-300x66.png)](http://ianoxley.com/wp-content/uploads/2010/04/Screenshot-Webkit-Notifications-API-request-permission1.png)

After that, you should see the notifications stack up in the bottom right-hand corner of your screen:

[![Screenshot of the notifications](http://ianoxley.com/wp-content/uploads/2010/04/Screenshot-notifications1-300x168.png)](http://ianoxley.com/wp-content/uploads/2010/04/Screenshot-notifications1.png)

At the time of writing, you'll need to be using Google Chrome for the demo to work (although I'm pretty sure that support for the Notifications API in Safari is imminent).

And, as an aside, I managed to throw a bit of HTML 5 into the demo as well with some [autofocus](http://dev.w3.org/html5/spec/Overview.html#autofocusing-a-form-control) and [placeholder](http://dev.w3.org/html5/spec/Overview.html#the-placeholder-attribute) attributes on the `<input type="text" />` field, just for good measure :)
