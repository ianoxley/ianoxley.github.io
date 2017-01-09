---
date: '2009-07-06 15:15:54'
layout: post
slug: e-text-editor-and-the-ruby-no-such-file-to-load-rubygems-error
status: publish
title: 'E Text Editor and the ruby: no such file to load rubygems error'
wordpress_id: '101'
categories:
- devtools
tags:
- cygwin
- devtools
- e text editor
- ruby
---

So, you are using the [e text editor](http://www.e-texteditor.com/) and try to run a bundle only to be confronted with the following:

> ruby: no such file to load -- ubygems (LoadError) ruby: no such file to load -- ubygems (LoadError)

After doing some [digging](http://www.google.co.uk/search?q=ruby%3A+no+such+file+to+load+--+ubygems+%28LoadError%29+ruby%3A+no+such+file+to+load+--+ubygems+%28LoadError%29+&ie=utf-8&oe=utf-8&aq=t&rls=org.mozilla:en-US:official&client=firefox-a) it turns out the cause is the **RUBYOPT=-rubygems** environment variable that is set by the [Windows one-click Ruby installer](http://rubyinstaller.rubyforge.org/wiki/wiki.pl?RubyInstaller). Now, if you have not got rubygems installed you might be able to get away with simply [unsetting the RUBYOPT environment variable](http://www.xerxesb.com/2009/e-text-editor-ruby-no-such-file-to-load-ubygems-loaderror/) (although YMMV).

However, as e text editor makes use of Ruby via [Cygwin](http://www.cygwin.com/), another solution is to [modify your **.bashrc** file](http://www.e-texteditor.com/forum/viewtopic.php?t=1091):

>     Try this:
>     
>     Go to the cygwin bash prompt.  If you don't know how to get there, use Start -> Run -> c:\cygwin\cygwin.bat.
> 
>     Type:
>     echo unset RUBYOPT >> .bashrc
>     
>     Type:
>     . .bashrc
> 
>     Type:
>     irb
> 
>     If you see:
>     irb(main):001:0>
> 
>     You should be good to go.

But what worked for me - and I don't know whether this has anything to do with me having Ruby installed under Windows and under Cygwin - was making the same changes to .bashrc outlined above to my **.profile** script (so simply replace _.bashrc_ with _.profile_ in the quoted text above).

Hopefully at least one of these methods should work for you.
