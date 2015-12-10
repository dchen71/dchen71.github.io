---
layout: page
title: Archive
---

## Blog Posts

{% for post in site.posts %}
	{% capture year2015 %}{{post.date | date: "%Y"}}{% endcapture %}
  
	{% if forloop.first %}
	<h3>{{year2015}}</h3>
	<ul>
	{% endif %}
	<li>{{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})</li>
	</ul>
  
{% endfor %}