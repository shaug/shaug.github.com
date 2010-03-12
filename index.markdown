---
layout: default
title: shaug's blog
---

{% for post in site.posts limit:1 %}
<em>Posted on {{ post.date | date_to_string }}.</em>
<h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
{{ post.content }}
{% endfor %}
