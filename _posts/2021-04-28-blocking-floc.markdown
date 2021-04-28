---
layout: post
title: Blocking FLoC
date: 2021-04-28
tags:
  -html
  -google
  -floc
---
Google's new Federated Learning of Cohorts (FLoC) venture [hasn't exactly been warmly received](https://www.eff.org/deeplinks/2021/03/googles-floc-terrible-idea).

There are several ways to [prevent your site from becoming part of the FLoC network](https://paramdeo.com/blog/opting-your-website-out-of-googles-floc-network), you just need to pick the one most appropriate for your setup. As I host this site on GitHub Pages, all I needed to do was add a `<meta>` tag to the head of my page like so:

```html
<meta http-equiv="Permissions-Policy" content="interest-cohort()">
```

<span lang="fr">Et voil&#0224;!</span> FLoC off.
