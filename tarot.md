---
layout: default
title: "Tarot"
permalink: /tarot/
---

<h1>Tutti i post della categoria <tarot></h1>

{% for post in site.posts %}
  {% if post.categories contains 'tarot' %}
    <h2>{{ post.title }}</h2>
    <p>{{ post.content }}</p>
  {% endif %}
{% endfor %}