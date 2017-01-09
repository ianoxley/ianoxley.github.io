---
date: '2010-08-05 23:43:11'
layout: post
slug: detecting-a-drupal-users-first-login
status: publish
title: Detecting A Drupal Users First Login
wordpress_id: '415'
categories:
- web
tags:
- drupal
- php
---

Being fairly new to Drupal, I was interested to know whether it had anything built in that let you know, or detect, when a user was logging in for the first time e.g. to show them a welcome message.

As far as I know, there's no method in the API to detect this. However, after checking the `global $user` object's properties to see what we had to play with, it turns out it wasn't all that tricky:
	
  * the `$global user` contains 3 timestamp properties: `created`, `access` and `login`
  * when a user logs in for the first time, all 3 of these timestamps are equal

This means we can check whether a user is logging in for the first time with something like this:
    
    function is_first_time_login($user) {
      return ($user->created == $user->login) && 
             ($user->login == $user->access);
    }

Now we can call that function where we need to in our elsewhere in our code. For example:
    
    function foo() {
      global $user;
      ...
      if (is_first_time_login($user)) {
        drupal_set_message(WELCOME_MSG);
      }
      ...	
    }

So far, this approach seems to be working quite well :)
