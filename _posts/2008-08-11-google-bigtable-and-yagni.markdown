---
date: '2008-08-11 20:27:09'
layout: post
slug: google-bigtable-and-yagni
status: publish
title: Google, BigTable and YAGNI
wordpress_id: '29'
tags:
- agile
- google
---

[YAGNI](http://en.wikipedia.org/wiki/You_Ain%27t_Gonna_Need_It) - short for "You Aren't Going to Need It" - is the acronym given to not writing code until you are sure you are actually going to need it. While reading Google's paper on BigTable the other day it was interesting to read that this was one of the lessons learned during its development:

> Another lesson we learned is that it is important to delay adding new features until it is clear how the new features will be used. For example, we initially planned to support general-purpose transactions in our API. Because we did not have an immediate use for them, however, we did not implement them.
