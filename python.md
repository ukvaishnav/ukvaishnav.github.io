---
layout: page
title: Python
---
<ul>

{% for post in site.categories.python %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}

</ul>