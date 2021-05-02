---
layout: page
title: Python
---

{% for post in site.categories.python %}
    <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}
