---
layout: layout
title: Archive
permalink: /archive/
---

<h2>Archive</h2>
<ul>
  {% for post in site.posts %}

    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

    <li>{{ post.date | date:"%b %e" }} <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>