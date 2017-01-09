---
layout: post
title: "Parsing the UNIX timestamp from an ASP.NET JSON-serialised DateTime"
date: 2012-03-23 20:57
comments: true
categories: [asp.net,javascript]
---

Scott Hanselman posted an article recently about the fun that is [parsing
a JSON-serialised
DateTime](http://www.hanselman.com/blog/OnTheNightmareThatIsJSONDatesPlusJSONNETAndASPNETWebAPI.aspx). Basically, instead of a DateTime being
JSON-serialised to something like `2012-03-08T23:12:45`, you end up with what
looks like a JavaScript regex in the form `/Date11134446542/`.

I came across this problem the other week and wrote this little function in
JavaScript to parse the JSON into a Date object:

[https://gist.github.com/ianoxley/1993182](https://gist.github.com/ianoxley/1993182)
