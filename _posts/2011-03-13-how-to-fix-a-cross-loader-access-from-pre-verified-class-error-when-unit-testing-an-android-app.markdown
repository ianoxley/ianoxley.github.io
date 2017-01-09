---
date: '2011-03-13 00:59:34'
layout: post
slug: how-to-fix-a-cross-loader-access-from-pre-verified-class-error-when-unit-testing-an-android-app
status: publish
title: How to fix a cross-loader access from pre-verified class error when unit testing
  an Android app
wordpress_id: '467'
categories:
- mobile
tags:
- android
- java
- junit
---

When trying to run some Android unit tests, I was getting a `java.lang.IllegalAccessError: cross-loader access from pre-verified class` error. After Googling I came across [this helpful answer](http://stackoverflow.com/questions/2431457/why-do-i-get-a-illegal-access-error-when-running-my-android-tests/2434818#2434818) on Stack Overflow, which linked through this article: [Android Testing: External Libraries](http://dtmilano.blogspot.com/2009/12/android-testing-external-libraries.html)

Basically, the problem was being caused by me using an external jar file in my project and unit tests. There were 2 steps I needed to follow to fix things:

  1. Export the external jar file from the main project i.e. _not_ the test project
  2. Remove the [reference to the external jar file](http://dtmilano.blogspot.com/2009/12/android-testing-external-libraries.html?showComment=1286842519439#c3733652962358358725) from my test project

Et voila - my unit tests were up and running. Getting them all to pass was another matter though :)
