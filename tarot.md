---
layout: default
title: "Tutti i post della categoria 1"
permalink: /tarot/
---

<h2>Tutti i post della categoria 1</h2>

<ul>
{% for post in site.tarot %}
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
