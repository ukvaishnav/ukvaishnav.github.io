---
layout: page
title: Projects
mathjax: true
---

<ul>

{% for post in site.categories.physics %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}

</ul>
