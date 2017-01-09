---
date: '2009-07-20 21:57:36'
layout: post
slug: c-sharp-string-extension-methods
status: publish
title: C# String Extension Methods
wordpress_id: '115'
categories:
- asp.net
- c#
---

There are quite a few instances where string operations in C# seem slightly verbose. So, I had a play around with extension methods the other day to see if I could come up with some alternate ways of doing some pretty standard operations but with a touch more syntactic sugar sprinkled on the top.

For example, rather than using `string.IsNullOrEmpty` it makes much more sense to me to call `IsNullOrEmpty` on the string you want to check instead:
    
    // Checking for a null or empty string in C#
    if (string.IsNullOrEmpty(foo)) {
        ...
    }
    
    // versus
    if (foo.IsNullOrEmpty()) {
        ...
    }

Also, I thought it would be nicer if you could call some of the static `Regex` methods directly on string objects:
    
    // Instead of this
    if (Regex.IsMatch(foo, @"[a-zA-Z]+")) {
        ...
    }
    
    // You could just do this
    if (foo.IsMatch(@"[a-zA-Z]+")) {
        ...
    }

I have created a gist of these methods, plus a few others:

[http://gist.github.com/111696](http://gist.github.com/111696)

Are there any other string operations that you think should be included? If you have any suggestions, please leave a comment.
