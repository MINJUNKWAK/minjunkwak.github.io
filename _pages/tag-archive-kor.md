---
layout: archive
permalink: /tags-kor/
title: "Posts by Tags"
author_profile: true
ref: tag-archieve
lang: Korean
---

{% include group-by-array collection=site.posts field="tags" %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% for post in posts %}
    {% if post.lang=='Korean' %}
      {% include archive-single.html %}
    {% endif %} 
  {% endfor %}
{% endfor %}