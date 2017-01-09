---
date: '2008-02-29 23:52:37'
layout: post
slug: setting-up-the-silverlight-dlrconsole-on-apache
status: publish
title: Setting up the Silverlight DLRConsole on Apache
wordpress_id: '10'
tags:
- ironpython
- silverlight
---

If, like me, you fancied playing around with IronPython and Silverlight on Apache, here's how I got mine set-up:
	
  1. Download and unpack DLRConsole.zip from [http://silverlight.net/Samples/1.1/DLR-Console/DLRConsole.zip](http://silverlight.net/Samples/1.1/DLR-Console/DLRConsole.zip)
  2. Added the following to my Apache httpd.conf file:
    
    <VirtualHost 127.0.0.1>
        ServerName DLRConsole
        DocumentRoot "C:/dev/DLRConsole"
        AddType text/python .py
        AddType text/jscript .jsx

        DirectoryIndex index.htm index.html
    </VirtualHost>
    
    <Directory "C:/dev/DLRConsole">
        Options Indexes MultiViews
        AllowOverride None
        Order allow,deny
        Allow from all

        DirectoryIndex index.htm index.html
    </Directory>
	
  3. I also set up the following in my hosts file (typically located on Windows at C:WINDOWSSYSTEM32DRIVERSETCHOSTS):

    127.0.0.1 dlrconsole

  4. Re-start Apache and point your browser to http://dlrconsole

You may need to comment out any other Python handlers in you httpd.conf file and add them on a per `<Directory>` basis, but if you’ve got loads of Python-based sites on your Apache installation then your mileage may vary. Fortunately this wasn’t an issue for me so the following was sufficient:

    AddHandler cgi-script .pl
    #AddHandler cgi-script .py

For more on the DLRConsole see [this article](http://msdn2.microsoft.com/en-us/magazine/cc163284.aspx) from MSDN Magazine.
