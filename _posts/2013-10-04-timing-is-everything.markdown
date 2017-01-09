---
layout: post
title: "Timing is Everything"
date: 2013-10-04 23:56
comments: true
categories: [JavaScript, Jasmine]
---

I had a problem with some Jasmine tests the other day that used the Jasmine Mock Clock. The code under test displayed a countdown timer, and the tests checked that the minutes and seconds counted down after each second, and handled the transition from 2 minutes to 1 minute 59 seconds, etc. correctly. Every time the tests ran, the first test that used the Jasmine Mock Clock would fail, but the rest would pass.

As it turned out, the cause of this was initialising the Jasmine Mock Clock one line too late.

The code under test was a jQuery UI widget, which used `setInterval` internally to update it's display. I used `beforeEach` to setup my tests, create the widget instance, and initialse the Jasmine Mock Clock:

    // Before: test was failing
    var widget;
    ...
	beforeEach(function() {
        ...
		widget = $('#foo').countdown();
		jasmine.Clock.useMock();
		...
    });

The line `widget = $('#foo').countdown()` instantiates the countdown widget, and it begins to countdown straight away. But its using `window.setInterval` internally as `jasmine.Clock.useMock()` doens't get called until the next line. By swapping these two lines around, the Jasmine Mock Clock is always used, and all the tests pass.

    // After: all tests pass
    var widget;
    ...
	beforeEach(function() {
        ...
		jasmine.Clock.useMock();
		widget = $('#foo').countdown();
		...
    });

