---
title: Posts
layout: category
permalink:  /categories/posts/
taxonomy: posts
---

{% for post in site.categories.Posts %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}