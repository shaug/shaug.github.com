---
layout: default
title: bosshaug
---

{% for post in site.posts limit:1 %}
<h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
{{ post.content }}
<em>Posted on {{ post.date | date_to_string }}.</em>
{% endfor %}
