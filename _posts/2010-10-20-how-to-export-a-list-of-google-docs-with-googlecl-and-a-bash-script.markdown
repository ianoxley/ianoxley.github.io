---
date: '2010-10-20 23:40:43'
layout: post
slug: how-to-export-a-list-of-google-docs-with-googlecl-and-a-bash-script
status: publish
title: How to Export a List of Google Docs With GoogleCL and a Bash Script
wordpress_id: '439'
categories:
- web
tags:
- google
- web
---

I was playing around with [GoogleCL](http://code.google.com/p/googlecl/) recently and came up with this: [http://github.com/ianoxley/googlecl-export](http://github.com/ianoxley/googlecl-export)

It's a Bash script that lets you export a list of Google Docs to a specified format. For example, to export a particular folder to PDF you'd type something like this:
    
    googlecl-export -f pdf -d yourfolderofdocs

You need to have GoogleCL installed for the Bash script to work (GoogleCL can be downloaded from [http://code.google.com/p/googlecl/](http://code.google.com/p/googlecl/)) but otherwise you should just need to make the script executable e.g. `chmod u+x googlecl-export` and possibly stick it somewhere on your `$PATH`
