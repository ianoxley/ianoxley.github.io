---
layout: post
title: "Installing Mercurial 2.1 on IIS 7"
date: 2012-05-02 00:03
comments: true
categories: [mercurial,iis]
---

If you ever need to set up Mercurial on Windows Server 2008 R2 then you should read Jeremy Skinner's [Setting up Mercurial on IIS7](http://www.jeremyskinner.co.uk/mercurial-on-iis7/). It's a great article that guides you every step of the way, from installing Mercurial and Python, to configuring IIS and setting up SSL. 

Because I was using later versions of Mercurial and Python than those used in
the guide (I was using Mercurial 2.1 and Python 2.6; there's a note in the
guide stating it used Mercurial 1.4.3 with Python 2.5.4, and should work with
Mercurial 1.5 and Python 2.6.4), there were a couple of problems I
had to workaround - if you're using similar versions of Mercurial and Python
to me then hopefully this'll help you out, although YMMV:

1. Since Mercurial 1.6+, `hgwebdir.cgi` has been merged with `hgweb.cgi`. Therefore wherever the article mentioned `hgwebdir.cgi`, I swapped it for `hgweb.cgi`.

2. After extracting `library.zip` to `C:\inetpub\wwwroot\hg`, and copying the `templates` folder to `C:\inetpub\wwwroot\hg`, I tried to access `http://name_of_server/hg/hgweb.cgi` but Python threw an `ImportError` and complained it couldn't find the mercurial module. To get round this I:
    * Reverted the previous copy and extract steps i.e. removed the `templates` folder, and the extracted `library.zip`, from `C:\inetpub\wwwroot\hg`
    * Downloaded `mercurial-2.1.1.win-amd64-py2.6.exe` from [https://bitbucket.org/tortoisehg/thg-winbuild/downloads/](https://bitbucket.org/tortoisehg/thg-winbuild/downloads/) and ran the installer (__NB__ you should download the .exe most appropriate for your server). This found the version of Python installed on my system and copied the relevant libraries / modules to Python's site-packages folder. I was then able to browse to `http://name_of_server/hg/hgweb.cgi` without any problems.


