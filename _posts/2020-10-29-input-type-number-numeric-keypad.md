---
layout: post
title: Displaying the Numbers Only Keypad for HTML <input type="number">
date: 2020-10-29
tags:
  -html
  -til
---

It turns out that `<input type="number">` isn't enough on its own to get
a mobile / touchscreen device to display a numbers only keypad. By default
you'll get the punctuation symbols too:

``` html
<label for="numbers-and-special-chars">Enter numeric code</label>
<input id="numbers-and-special-chars" type="number">
```

To get the number only keypad you also need to add the `pattern` attribute, and
set its value to `[0-9]*` like this:

``` html
<label for="numbers-only">Enter numeric code</label>
<input id="numbers-only" type="number" pattern="[0-9]*">
```
