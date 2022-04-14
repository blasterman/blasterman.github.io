---
title: Projects
layout: category
permalink: /categories/projects/
taxonomy: projects
---

{% for post in site.categories.Projects %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}