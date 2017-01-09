---
date: '2011-02-03 22:54:39'
layout: post
slug: 2-things-i-learnt-about-javascript-this-week
status: publish
title: 2 Things I Learnt About JavaScript This Week
wordpress_id: '464'
categories:
- javascript
tags:
- javascript
---

I recently picked up a copy of [JavaScript: The Good Parts](http://www.amazon.co.uk/gp/product/0596517742?ie=UTF8&tag=strasanox-21&linkCode=as2&camp=1634&creative=19450&creativeASIN=0596517742)![](http://www.assoc-amazon.co.uk/e/ir?t=strasanox-21&l=as2&o=2&a=0596517742) and have been reading it on the train to and from work. Although the book's preface states that the book is targeted at programmers who are venturing into JavaScript for the first time or who have been working with JavaScript at a novice level I'm still finding it enjoyable to read and am managing to pick up a few tips along the way.

Two such tips that I picked up this week are:
	
  1. When using the `throw` statement you can use an object literal to give an exception a type and a message. For example:

    throw {
      type: 'FooError',
      message: 'Invalid foo'
    };
	
  2. When using closures, avoid creating an anonymous function inside a loop as it can be computationally wasteful and potentially lead to confusing code. For example (this is taken from the book):
    
    var add_the_handlers = function (nodes) { 
    	var helper = function (i) {
    		return function (e) { 
    			alert(i);
    		};
    	}; 
    	
    	var i; 
    	for (i = 0; i < nodes.length; i += 1) {
    		nodes[i].onclick = helper(i);
    	}
    };	
	
