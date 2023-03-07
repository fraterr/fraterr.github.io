---
layout: default
title: "Tarot"
permalink: /tarot/
---

{% for post in site.categories.tarot %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}