---
date: '2010-01-08 18:18:44'
layout: post
slug: how-to-check-if-an-assembly-was-compiled-in-debug-or-release-mode
status: publish
title: How to check if an assembly was compiled in debug or release mode
wordpress_id: '276'
categories:
- devtools
tags:
- ironpython
---

I came across this [nifty bit of code](http://chillijam.co.uk/2006/05/04/determine-if-an-assembly-is-a-debug-or-release-build/) the other day when looking for a way to do this and, just for fun, thought I'd convert it to [IronPython](http://ironpython.net/). So I did. And here it is:
    
    import System
    
    def is_assembly_debug_build(filename):
    	"""Returns true if filename appears to have been built in debug mode"""
    	result = False
    	dll = System.Reflection.Assembly.LoadFile(filename)
    	customAttribs = dll.GetCustomAttributes(False)
    	for att in customAttribs:
    		if att.GetType() == System.Type.GetType("System.Diagnostics.DebuggableAttribute"):
    			result = att.IsJITTrackingEnabled
    	return result

I saved this in a file called diagnostics.py. So using it (you'll need to be in the same directory as diagnostics.py or have added diagnostics.py to your path - more info can be found here: [http://docs.python.org/tutorial/modules.html#the-module-search-path](http://docs.python.org/tutorial/modules.html#the-module-search-path)) is simply a matter of doing something like this:
    
    from diagnostics import is_assembly_debug_build
    is_assembly_debug_build([absolute_path_to_your_dll])

If you're interested you can grab a copy of diagnostics.py from [http://gist.github.com/206177](http://gist.github.com/206177)
