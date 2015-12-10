---
layout: page
title: Archive
---

## Blog Posts

{% for post in site.posts %}
   { % capture year2015 %}{{post.date | date: "%Y"}}{% endcapture %}
   ###2015
   {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}