---
layout: page
title: Photography
permalink: /photography/
description: Selected photography work.
nav: true
nav_order: 2
---

<div class="projects">
  <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
    {% assign photo_files = site.static_files | where_exp: "file", "file.path contains '/assets/img/photography/'" | sort: "path" %}
    {% for photo in photo_files %}
      {% assign ext = photo.extname | downcase %}
      {% assign is_generated_webp = false %}
      {% if photo.name contains "-480.webp" or photo.name contains "-800.webp" or photo.name contains "-1400.webp" %}
        {% assign is_generated_webp = true %}
      {% endif %}
      {% if is_generated_webp == false %}
        {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" or ext == ".gif" %}
          <div class="col">
            <div class="card h-100 hoverable">
              <img
                src="{{ photo.path | relative_url }}"
                class="card-img-top"
                alt="{{ photo.basename | replace: '-', ' ' | replace: '_', ' ' }}"
                loading="lazy"
              >
            </div>
          </div>
        {% endif %}
      {% endif %}
    {% endfor %}
  </div>
</div>
