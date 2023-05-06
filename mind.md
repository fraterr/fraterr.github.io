---
layout: default
title: Mind
---

<h1>Mind Posts</h1>

<ul>
{% for post in site.categories.mind %}
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
