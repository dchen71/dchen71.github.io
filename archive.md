---
layout: page
title: Archive
---

## Blog Posts

<ul>
  {% for post in site.posts %}

    {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
    {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
    {% if year != nyear %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% endif %}
   
    <li>{{ post.date | date_to_string }} &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>