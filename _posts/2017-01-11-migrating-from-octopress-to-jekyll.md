---
layout: post
title: Migrating from Octopress to Jekyll
date: 2017-01-11
tags: jekyll
---

I've been running my blog on Octopress for the past 3 years. It has served me
pretty well. But I couldn't shake the feeling that I was running my site on
someone else's Jekyll blog, as that - somewhat harshly - is what Octopress
essentially is.

So I decided to migrate my site to Jekyll itself. This turned out to be
reasonably straight forwards:

1. I installed Jekyll as per the instructions on
   [https://jekyllrb.com/](https://jekyllrb.com/)
    * `gem install jekyll`
    * `jekyll new my-site && cd $_`

2. Copied over the contents of my Octopress `source/_posts` to Jekyll's
   `_posts` directory

3. Copied over any static resources to the Jekyll root folder e.g. favicons,
   and if you're hosting on GitHub Pages as I am, your `CNAME` file.

And that was pretty much it!


