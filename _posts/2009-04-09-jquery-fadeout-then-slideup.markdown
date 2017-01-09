---
date: '2009-04-09 23:39:01'
layout: post
slug: jquery-fadeout-then-slideup
status: publish
title: jQuery fadeOut() Then slideUp()
wordpress_id: '63'
categories:
- javascript
tags:
- javascript jquery
---

After hastily answering [a question on stackoverflow.com regarding calling jQuery's slideUp() method after fadeOut()](http://stackoverflow.com/questions/734554/jquery-fadeout-then-slideup), what I thought to be a good answer turned out to be not quite so good afterall.  After reading the comments on my answer I decided to investigate to see what was wrong with my original solution.  Now, the problem that needed to be solved was the element below the faded-out element jumping up during the slide up: a nice smooth slide up was required. I initially thought you could accomplish this by calling fadeOut() with a callback function as the second parameter which would handle the slideUp(). Something like this:

    
    $('elementAbove').fadeOut(500, function() {
        $('elementBelow').slideUp();
    });


But you still get the jump up, rather than the nice smooth slide up that is desired.  In the comments to my answer it was suggested fading the element out to an opacity of 1%, then doing the slide up, would work. After checking the documentation, jQuery has a  fadeTo( speed, opacity, [callback] ) method which lets us do exactly this, then execute the slide up in our callback function.  So, given the following HTML:
    
    <ul id="menu">
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">News &amp; Events</a></li>
        <li><a href="#">Downloads</a></li>
        <li><a href="#">Contact Us</a></li>
    </ul>

We can achieve our desired effect like this:
    
    $(document).ready(function() {
        $('#menu a').click(function() {
            var $theParent = $(this).parent();
            $(this).fadeTo(500, 0.1, function() {
                $theParent.slideUp(750);
            });

     	return false;
        });
    });


You can [see this in action here](http://www.strongasanox.co.uk/demos/jquery-fade-out-slide-up.php).
