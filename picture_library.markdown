---
layout: page
title: Picture Library
permalink: /picture_library/
---

<div class="image-gallery">
  {% for file in site.static_files %}
    {% if file.path contains '/gallery/' %}
      {% assign filenameparts = file.path | split: "/" %}
      {% assign filename = filenameparts | last | replace: file.extname,"" %}
      <img class="gallery-image" src="{{ file.path | relative_url }}" alt="{{ filename }}" title="{{ filename }}" />
    {% endif %}
  {% endfor %}
</div>
