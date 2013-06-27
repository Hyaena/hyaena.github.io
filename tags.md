---
layout: page
permalink: /tags/index.html
title: Tags
tagline: Posts by tag
tags: [tags]
image:
  feature: texture-feature-03.jpg
---

<ul class="tag_box inline">
  {% assign tags_list = site.tags %}
  {% include hyaena/tags_list %}
</ul>


{% for tag in site.tags %}
  <h2 id="{{ tag[0] }}-ref">{{ tag[0] }}</h2>
  <ul>
    {% assign pages_list = tag[1] %}
    {% include hyaena/pages_list %}
  </ul>
{% endfor %}
