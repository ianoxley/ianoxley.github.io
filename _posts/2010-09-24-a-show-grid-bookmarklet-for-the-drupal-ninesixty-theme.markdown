---
date: '2010-09-24 13:42:35'
layout: post
slug: a-show-grid-bookmarklet-for-the-drupal-ninesixty-theme
status: publish
title: A Show Grid Bookmarklet for the Drupal ninesixty Theme
wordpress_id: '437'
categories:
- web
tags:
- drupal css 960 javascript
---

I've been using the Drupal ninesixty theme recently. One of the nice things about it is the ability to add a `show-grid` class to the `<body>` tag to display a grid as a background image grid for development / debugging.

But, rather than manually adding and removing this class to the page.tpl.php, I created a bookmarklet to toggle the `show-grid` class on and off. The code looks like this:

    (function() {
      if (document.body.className) {
        var b = document.body;
        if (b.className.indexOf(' show-grid') !== -1) {
          b.className = b.className.replace(' show-grid', '');
        } else {
          b.className += ' show-grid';
        }
      }
    })();

It _does_ make the assumption that your `<body>` tag will always have a `class` attribute, although it should be fairly straight forwards to modify the code to allow for cases where the `<body>` tag does _not_ have a `class` attribute.

To save it as a bookmarklet, drag this link to your bookmarks bar: [Show Grid](javascript:(function()%20{if%20(document.body.className)%20{var%20b%20=%20document.body;if%20(b.className.indexOf(%27%20show-grid%27)%20!==%20-1)%20{b.className%20=%20b.className.replace(%27%20show-grid%27,%20%27%27);}%20else%20{b.className%20+=%20%27%20show-grid%27;}}})();)
