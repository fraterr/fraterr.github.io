---
layout: default
title: "Tarot"
permalink: /tarot/
---

<h2>Tarot</h2>

<ul>
{% for post in site.tarot %}
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
