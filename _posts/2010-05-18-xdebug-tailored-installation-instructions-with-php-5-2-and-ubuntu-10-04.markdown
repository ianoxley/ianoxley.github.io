---
date: '2010-05-18 22:27:14'
layout: post
slug: xdebug-tailored-installation-instructions-with-php-5-2-and-ubuntu-10-04
status: publish
title: Xdebug Tailored Installation Instructions with PHP 5.2 and Ubuntu 10.04
wordpress_id: '356'
categories:
- devtools
tags:
- drupal
- php
- ubuntu
- xdebug
---

I was really impressed with the [Xdebug Tailored Installation Instructions](http://xdebug.org/find-binary.php) earlier today. Setting up a dev machine at [my new job](http://www.orangebus.co.uk/) wasn't going quite according to plan because, as nice as Ubuntu 10.04 Lucid Lynx is:
	
  1. Installing PHP via `sudo apt-get install php5` installs the latest version from the repositories (version 5.3 at the time of writing)
  2. We do a lot of work in Drupal, mostly version 6 which isn't compatible with PHP 5.3 (and quite a few modules that work with Drupal 6 don't work with Drupal 7 apparently - Drupal 7 plays a lot nicer with PHP 5.3 by all accounts).
  3. So it was necessary to uninstall all the PHP 5.3 packages, [add the karmic repositories to the sources.list](http://ohioloco.ubuntuforums.org/showpost.php?p=9080474&postcount=7) then reinstall PHP - this time PHP 5.2

Once all this was done, it was time to install Xdebug. The tailored installation instructions seemed the best option as I'd just had to revert to a previous version of PHP. And, it couldn't have been simpler or more straight-forward to do:
	
  1. Go to [http://xdebug.org/find-binary.php](http://xdebug.org/find-binary.php), paste in the HTML from your `phpinfo()` output and submit the form
  2. You'll get a nice summary and some instructions to follow :)

[caption id="attachment_358" align="aligncenter" width="150" caption="Summary"][![Summary](http://www.strongasanox.co.uk/wp-content/uploads/2010/05/xdebug_summary-150x150.jpg)](http://www.strongasanox.co.uk/wp-content/uploads/2010/05/xdebug_summary.jpg)[/caption]

[caption id="attachment_359" align="aligncenter" width="150" caption="Instructions"][![Instructions](http://www.strongasanox.co.uk/wp-content/uploads/2010/05/xdebug_instructions-150x150.jpg)](http://www.strongasanox.co.uk/wp-content/uploads/2010/05/xdebug_instructions.jpg)[/caption]

After following the instructions, restart apache and reload your `phpinfo()` page: if your experience is anything as good as mine you should see all the xdebug configuration options set up nicely and ready to go.
