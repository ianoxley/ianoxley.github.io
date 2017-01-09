---
date: '2009-03-31 22:47:28'
layout: post
slug: accessible-html-for-x-out-of-y-results-summaries
status: publish
title: Accessible HTML for X-out-of-Y Results Summaries
wordpress_id: '58'
categories:
- accessibility
tags:
- accessibility
- html
---

The project I am currently involved with at work has several paging widgets i.e. for image slideshows, search results, etc. that contain summary information such as "Showing 1/8".

So how can this information be marked up in HTML in an accessible manner?

Well, I cannot remember where I got the inspiration for this from - if I remember I will post an update - but here is the HTML that I decided to use:
    
    <span class="summary">
        Showing 1<abbr title="out of a total of">/</abbr>8
    </span>

Pretty nifty eh?

Please let me know what you think.
