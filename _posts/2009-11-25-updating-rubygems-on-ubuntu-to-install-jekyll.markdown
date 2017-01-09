---
date: '2009-11-25 00:10:05'
layout: post
slug: updating-rubygems-on-ubuntu-to-install-jekyll
status: publish
title: Updating RubyGems on Ubuntu to Install Jekyll
wordpress_id: '242'
categories:
- web
tags:
- jekyll
- ruby
- rubygems
- ubuntu
---

Having recently [read about Jekyll](http://articles.sitepoint.com/article/jekyll-sites-made-simple) I decided to boot up Ubuntu, install all the bits and pieces and give it a try. However, I fell at the first hurdle when greeted by the following error:

> Error installing gemcutter:
> gemcutter requires RubyGems version >= 1.3.5

The Synaptic Package Manager reported everything as being _up-to-date_ but only to version 1.3.1. As it turns out, there is another way to [update rubygems on Ubuntu](http://rudygems.com/post/164224985/update-rubygems-on-ubuntu), which worked a treat! The rest of the installation was a breeze :-)

If you are interested more info on Jekyll can be found on [GitHub](http://github.com/mojombo/jekyll).
