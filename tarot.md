---
layout: default
title: "Tarot"
permalink: /tarot/
---


{% for post in site.posts %}
  {% if post.categories contains 'tarot' %}
    <h2>{{ post.title }}</h2>
    <p>{{ post.content }}</p>
  {% endif %}
{% endfor %}