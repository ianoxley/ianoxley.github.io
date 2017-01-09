---
layout: post
title: "How to Disable Browser Link in Visual Studio 2013"
date: 2014-10-21 21:27:36 +0100
comments: true
categories: ASP.NET
---

As useful as it can be, sometimes you just need to turn [Browser Link] [1] off. There are two ways to do this in your `Web.config` file:

- Add the `vs:EnableBrowserLink` to your `<appSettings>` and set it's value to `false`:

``` xml
<appSettings>
	<add key="vs:EnableBrowserLink" value="false" />
</appSettings>
```

- Set the value of `debug` in the `<compilation>` tag to `false`:

``` xml
<system.web>
	<compilation debug="false" targetFramework="4.5" />
</system.web>
```

[1]: http://www.asp.net/visual-studio/overview/2013/using-browser-link "Using Browser Link"
