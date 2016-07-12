---
layout: post
title:  "Wordpress Order Query Multiple Meta"
date:   2016-07-12 02:37:00 +0200
categories: wordpress
---
For thosse who are using wordpress with [ACF][link1], if you want to sort posts with multiple meta keys, give key names in 'meta_query' as follows.


{% highlight php startinline linenos=table%}
<?php
$args = array(
	'post_type' => 'schedule',
	'post_status' => 'publish',
	'orderby' => array(
	'schedule-date' => 'ASC',
	'time'    => 'ASC',
	),
	'posts_per_page' => -1,
	'meta_query' => array(
		'schedule-date' => array(
			'key' => 'schedule-date',
			'value' => date("Ymd", strtotime("-1 days")),
			'type' => 'NUMERIC',
			'compare' => '>'
		),
		'time' => array(
			'key' => 'time',
			'value' => '',
			'compare' => 'LIKE'
		),
	)
);
{% endhighlight %}

Reference: [http://www.keybored.fr/2016/01/11/Wordpress-Order-Query-Multiple-Meta.html][link2].

[link1]:      https://www.advancedcustomfields.com/
[link2]:      http://www.keybored.fr/2016/01/11/Wordpress-Order-Query-Multiple-Meta.html