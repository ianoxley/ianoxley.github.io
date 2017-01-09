---
date: '2008-06-09 21:49:42'
layout: post
slug: jquery-form-focus-plugin-released
status: publish
title: jQuery Form Focus Plugin Released
wordpress_id: '21'
categories:
- javascript
tags:
- javascript
- jquery
- plugin
---

I have released the first version of my [jQuery Form Focus plugin](http://plugins.jquery.com/project/FormFocus). This lets you set the initial focus on any form element but is careful not to set the focus if the user has already [started filling in the form](http://www.themaninblue.com/writing/perspective/2005/10/27/). To use it you call something like:

    $('#username').formFocus();
    $('form input:first').formFocus();
    $('form#options input[type="checkbox"]:first').formFocus();

Hope you find it useful.
