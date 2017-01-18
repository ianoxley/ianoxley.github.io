---
layout: post
title: Migrating from Octopress to Jekyll
date: 2017-01-11
tags: jekyll
---

I've been running my blog on Octopress for the past 3 years. It has served me
well. But I couldn't shake the feeling that my site was running on
someone else's Jekyll blog, as that - somewhat harshly - is what Octopress
essentially is.

So I decided to migrate my site to Jekyll itself. This turned out to be
reasonably straight forwards:

1. I installed Jekyll as per the instructions on
   [https://jekyllrb.com/](https://jekyllrb.com/)
    * `gem install jekyll`
    * `jekyll new my-site && cd $_`

2. Copied my Octopress `source/_posts` directory to Jekyll's
   `_posts` directory

3. Copied my static resources to the Jekyll root folder e.g. favicons and my
   `CNAME` file.

And that was it!
