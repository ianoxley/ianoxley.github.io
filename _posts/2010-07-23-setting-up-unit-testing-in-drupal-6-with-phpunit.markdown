---
date: '2010-07-23 13:34:13'
layout: post
slug: setting-up-unit-testing-in-drupal-6-with-phpunit
status: publish
title: Setting up Unit Testing in Drupal 6 with PHPUnit
wordpress_id: '401'
categories:
- web
tags:
- drupal
- git
- php
- phpunit
---

I've been using Drupal now for a couple of months, ever since I started my [new job](http://www.orangebus.co.uk/), and the other day got my first chance to start writing a custom module.

I was keen to use a TDD approach, but wasn't sure how well this would play with Drupal. The [SimpleTest module](http://drupal.org/project/simpletest) looked pretty good but in the end I went with [PHPUnit](http://www.phpunit.de/), mainly because I'd used it before.

After a bit of research I came across a this post explaining how to get PHPUnit set up to play nicely with Drupal 6: [http://kristiannissen.wordpress.com/2009/12/08/drupal-6-phpunit-testing-setup/](http://kristiannissen.wordpress.com/2009/12/08/drupal-6-phpunit-testing-setup/)

It worked like a charm :) So, just for good measure, I created a project template containing the `unittests` folder and necessary include files and stuck it on GitHub: [http://github.com/ianoxley/drupal-phpunit-template](http://github.com/ianoxley/drupal-phpunit-template)
