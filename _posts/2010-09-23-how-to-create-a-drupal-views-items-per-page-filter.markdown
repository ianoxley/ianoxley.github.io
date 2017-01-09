---
date: '2010-09-23 23:16:08'
layout: post
slug: how-to-create-a-drupal-views-items-per-page-filter
status: publish
title: How to Create a Drupal Views Items Per Page Filter
wordpress_id: '435'
categories:
- web
tags:
- drupal
---

Sometimes, depending on the site you are working on, you need to allow (or the client _wants_ you to allow ;)) visitors to be able to select how many items per page will be displayed e.g. on a product listings page.

To do this in Drupal 6 turned out to be a lot easier than I thought. I used the code from [this blog post by Nicholas Coates](http://foreverheavy.com/10-quick-and-dirty-drupal-tips/#itemsperpage) but, rather than add it to a views template, I added it to a [hook_views_query_alter](http://drupalcontrib.org/api/function/hook_views_query_alter/6) function I was already using. This meant I could easily use the `$view` object passed as a parameter to this function:
    
    function hook_views_query_alter(&$view, &$query) {
      ...
      $itemCount = $_GET['itemcount']; // this is just as an example
      if ($itemCount == 0) {
        $view->set_items_per_page(10);
      } else {
        $view->set_items_per_page($itemCount);
      }
    	...
    }
    		
As Nicholas Coates says in his aforementioned blog post: this is a quick and painless way to implement an items per page filter.

