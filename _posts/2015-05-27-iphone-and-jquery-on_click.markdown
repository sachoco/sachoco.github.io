---
layout: post
title:  "iPhone and jQuery .on('click')"
date:   2015-05-27 16:36:00
categories: jquery iphone
---
In some situations you want to use jQuery .on method with elements to be filtered as follows.

{% highlight javascript %}
jQuery(document).on('click',selector, function(){  });
{% endhighlight %}

However, strangely this fails on iOS Safari browser if the target (or filtered) element doesn't have the CSS property "cursor: pointer;".

**Some Testing** (please test with iPhone)

<p data-height="368" data-theme-id="0" data-slug-hash="BNQvyZ" data-default-tab="result" data-user="sachoco" class='codepen'>See the Pen <a href='http://codepen.io/sachoco/pen/BNQvyZ/'>BNQvyZ</a> by Satoshi Shiraishi (<a href='http://codepen.io/sachoco'>@sachoco</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

I couldn't find much resources about this issue on the web but I believe I'm not the one of few who had a difficulty finding the cause.

Reference: [http://www.quirksmode.org/blog/archives/2010/10/click_event_del_1.html][link].


[link]:      http://www.quirksmode.org/blog/archives/2010/10/click_event_del_1.html