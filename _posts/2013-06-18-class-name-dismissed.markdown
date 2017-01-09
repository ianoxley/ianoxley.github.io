---
layout: post
title: "class(Name) Dismissed"
date: 2013-06-18 22:14
comments: true
categories: javascript
---
Back in the day, if you need to add, change, or remove a class on a HTML element, you'll have had little choice but to use the [className](https://developer.mozilla.org/en-US/docs/Web/API/element.className) property:

    el.className = 'foo';

    if (el.className === 'foo') {
	    el.className = 'bar';
    }
	
_[http://jsfiddle.net/ianoxley/YFfud/](http://jsfiddle.net/ianoxley/YFfud/)_
	
That was easy enough if an element had only one class applied to it, but things got trickier if you had multiple classes to contend with:

    var allClasses = el.className.split(/\s/);
    for (var i = 0, length = allClasses.length; i < length; i++) {
	    if (allClasses[i] === 'foo') {
		    allClasses[i] = 'bar';
		    break;
	    }
    }

    el.className = allClasses.join(' ');
	
_[http://jsfiddle.net/ianoxley/79TKR/](http://jsfiddle.net/ianoxley/79TKR/)_
	
Along came a slew of JavaScript libraries in the mid-2000's, with convenient methods for adding and removing classes:

    // Using jQuery
    var el = $('#element_id');
    el.addClass('foo');

    el.toggleClass('bar');

    if (el.hasClass('foo')) {
	    el.removeClass('foo');
    }
	
_[http://jsfiddle.net/ianoxley/HnVCV/](http://jsfiddle.net/ianoxley/HnVCV/)_
	
Now, in 2013, the latest version of each browser, with the exception of Opera Mini, all have [native support][1] for adding, removing, toggling, and checking if an element has a class applied, via the [classList](https://developer.mozilla.org/en-US/docs/Web/API/element.classList).

`classList` returns a token list (specifically a `DOMTokenList`) of all the classes applied to an element. It exposes a `length` property, and four functions:

* add - to add a class to the `classList`
* remove - to remove a class from the `classList`
* toggle - to add a class to the `classList`, or remove it if it's already there
* contains - to check if a class is in the `classList`

## classList Example

    <header id="main">...</header>
    ...
    <script>
	    var mainHeader = document.getElementById('main');
	    if (mainHeader.classList.length === 0) {
		    mainHeader.classList.add('foo');
	    }

	    mainHeader.classList.toggle('bar');

	    if (mainHeader.classList.contains('foo')) {
		    mainHeader.classList.remove('foo');
	    }
    </script>
_[http://jsfiddle.net/ianoxley/FVjgq/](http://jsfiddle.net/ianoxley/FVjgq/)_
	
One of the benefits of using the native `classList` API is performance. I tested the code from the above examples and the native code was [83% faster][2] than the jQuery equivalent:

![jsperf.com results](https://dl.dropboxusercontent.com/u/2234377/img/jsperf_classlist.png)

[Polyfills exist for older browsers](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills#classlist) that don't support classList natively, so if you need to support older browsers you'll have to judge whether they are a good fit for you, whether to write your own, or whether to fall back on your preferred JavaScript library.
	
[1]: http://caniuse.com/#search=classList  
[2]: http://jsperf.com/io-native-classlist-test

