---
layout: default
title: Tarot Posts
---

<h1>Tarot Posts</h1>

<ul>
{% for post in site.categories.tarot %}
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
