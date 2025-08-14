---
layout: page
title: Topics
permalink: /topics/
---

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">

<div class="list-group">
{% for t in site.data.topics.topics %}
  <a class="list-group-item list-group-item-action" href="{{ '/topics/' | append: t.slug | append: '/' | relative_url }}">{{ t.display }}</a>
{% endfor %}
</div>
