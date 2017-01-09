---
date: '2008-04-21 20:03:34'
layout: post
slug: data-binding-to-key-value-based-collections-in-aspnet
status: publish
title: Data Binding to Key-Value Based Collections in ASP.NET
wordpress_id: '18'
categories:
- asp.net
tags:
- asp.net
---

This is as much a note for me as anything as every time I need to data-bind a control to a [Hashtable](http://msdn2.microsoft.com/en-us/library/system.collections.hashtable.aspx) or a [Dictionary<TKey, TValue>](http://msdn2.microsoft.com/en-us/library/xfhwa508.aspx) I always find myself [reaching for Google](http://www.google.co.uk/search?hl=en&client=firefox-a&rls=org.mozilla%3Aen-US%3Aofficial&hs=HYh&q=asp.net+databinding+dictionary+hashtable&btnG=Search&meta=).

When data-binding to a key-value based collection you output data as follows:
	
    <%# Eval("Key") %> 

or
    
    <%# Eval("Value") %>

Simple really.
