---
date: '2008-10-03 19:53:02'
layout: post
slug: programmatically-getting-the-site-root-of-an-aspnet-web-application
status: publish
title: Programmatically Getting the Site Root of an ASP.NET Web Application
wordpress_id: '37'
categories:
- asp.net
tags:
- asp.net
---

If you ever find yourself needing to obtain the site root of your ASP.NET application you will hopefully find the following code useful:
    
    public string SiteRoot {
        get {
    	HttpRequest Request = HttpContext.Current.Request;
            string appPath = Request.ApplicationPath;
    	if (appPath.Length > 1) {
                appPath += "/";
            }
    
    	string portNum = string.Empty;
    	if(Request.Url.Port != 80) {
    	    portNum = string.Format(":{0}", Request.Url.Port);
    	}
    
    	return Request.Url.Scheme +
    	    "://" +
                Request.Url.Host +
                portNum +
                appPath;
        }
    }

On my last project it proved particularly useful as we could test it on our internal development servers before sending it across to the client; they themselves then ran the site on testing servers before deploying it onto their production server. All this was done without having to modify a single line of code or any configuration files.

If you are using ASP.NET 3.5 you could perhaps take this a stage further and implement this code as an [extension method](http://msdn.microsoft.com/en-us/library/ms364047(VS.80).aspx#cs3spec_topic3) on, for example, the HttpRequest object.

If you have any suggestions on how this can be improved please let me know.
