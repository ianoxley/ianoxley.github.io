---
date: '2011-01-08 00:10:12'
layout: post
slug: how-to-fix-a-mysql-packet-bigger-than-max_allowed_packet-bytes-error-error-1153
status: publish
title: How to fix a MySQL "packet bigger than 'max_allowed_packet' bytes" error (Error
  1153)
wordpress_id: '455'
categories:
- devtools
tags:
- mysql
---

I nearly always rely on the command line when moving data and / or schema changes between two different MySQL servers, exporting data with `mysqldump` then importing via something like:
    
    mysql -u foo -p dbname < script.sql

When running this the other day though I was presented with the following error:
	
> 
> ERROR 1153: Got a packet bigger than 'max_allowed_packet' bytes
> 

Fortunately help was at hand via [this forum post](http://forums.mysql.com/read.php?35,75794,253112#msg-253112). All I needed to do was run some SQL statements to set some global variables in MySQL like so:
    
    set global max_allowed_packet = 1000*1024*1024; 
    set global net_buffer_length = 1000000;
    	
To check whether this worked was merely a matter of running:

    -- should return 1048576000
    select @@max_allowed_packet;

Of course, you could always set the `max_allowed_packet` in your [`my.cnf` file](http://dev.mysql.com/doc/refman/5.1/en/option-files.html) instead.

### Update

After upgrading my MacBook Pro to OS X Snow Leopard, error 1153 was replaced with:
	
> ERROR 2006: MySQL server has gone away

Fortunately the above still fixed things. Of course, if I'd [listened to Phil Sherry](http://philsherry.com/2008/12/22/installing-mysql-for-mac-os-x-leopard-105/) in the first place I might not have had to re-install MySQL after upgrading OS X (although installing MySQL via the binary package installer _did_ seem to install in `/usr/local/bin` leaving me puzzled as to why it disappeared after the Snow Leopard upgrade. But that's a story for another day…).
  *[SQL]: Structured Query Language
