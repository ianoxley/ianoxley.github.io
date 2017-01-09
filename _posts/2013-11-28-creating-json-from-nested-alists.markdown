---
layout: post
title: "Creating JSON from nested alists"
date: 2013-11-28 21:58
comments: true
categories: 
published: false
---

So, I was trying to create a nested JSON object from a nested alist, and couldn't work out why my nested object was wrapped in an array:

	
	(json-encode '(("one" . 1)
				 ("two" . 2)
				 ("three" .
				  '(("three and a half" . "3.5")
					("three and three quarters" . "3.75")))))
