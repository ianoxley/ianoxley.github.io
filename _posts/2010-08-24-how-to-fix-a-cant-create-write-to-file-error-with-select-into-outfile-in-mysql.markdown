---
date: '2010-08-24 23:42:55'
layout: post
slug: how-to-fix-a-cant-create-write-to-file-error-with-select-into-outfile-in-mysql
status: publish
title: How to Fix a Can't Create/Write to File Error With SELECT INTO OUTFILE in MySQL
wordpress_id: '429'
categories:
- web
tags:
- mysql
---

Have you ever tried to use [`SELECT…INTO OUTFILE`](http://dev.mysql.com/doc/refman/5.1/en/select.html) in MySQL and come across the following error?

>		"Can't create/write to file '/path/to/folder/filename' (Errcode: 2)"

I was having this problem the other day and, after checking that file permissions weren't the cause of the problem, I came across the following [post on the MySQL forums](http://forums.mysql.com/read.php?20,369583,370808#msg-370808):

>		"The problem was not in MySQL but in AppArmor on Ubuntu. I had to add the directories I wanted to write into to my /etc/apparmor.d/usr.sbin.mysqld and restart apparmor.d."

So, one `sudo vim /etc/apparmor.d/usr.sbin.mysqld` later and I'd added the `path/to/folder` I needed to be able to write to (not forgetting to add the trailing comma ',' to the end of the line, which is _always_ required, even for the last line). 

All that was left to do was to restart AppArmor with:

    $ sudo /etc/init.d/apparmor restart

After that, `SELECT…INTO OUTFILE` worked like a charm :)
