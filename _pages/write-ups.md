---
title: Write-Ups
layout: category
permalink: /write-ups/
taxonomy: write-ups
---

{% for post in site.categories.Write-Ups %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}