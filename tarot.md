---
layout: default
title: "Tarot"
permalink: /tarot/
---


<ul>
{% for post in site.posts %}
  {% if post.categories contains 'tarot' %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endif %}
{% endfor %}
</ul>