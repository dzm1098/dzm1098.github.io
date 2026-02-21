---
layout: page
title: photography
permalink: /photography/
description: Selected photography work.
nav: true
nav_order: 2
---

This page automatically shows every image you upload to `assets/img/photography/`.

Supported formats: `.jpg`, `.jpeg`, `.png`, `.webp`, `.gif`.

<div class="projects">
  <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
    {% assign photo_files = site.static_files | where_exp: "file", "file.path contains '/assets/img/photography/'" | sort: "path" %}
    {% for photo in photo_files %}
      {% assign ext = photo.extname | downcase %}
      {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" or ext == ".gif" %}
        <div class="col">
          <div class="card h-100 hoverable">
            <img
              src="{{ photo.path | relative_url }}"
              class="card-img-top"
              alt="{{ photo.basename | replace: '-', ' ' | replace: '_', ' ' }}"
            >
            <div class="card-body">
              <p class="card-text">{{ photo.basename | replace: "-", " " | replace: "_", " " }}</p>
            </div>
          </div>
        </div>
      {% endif %}
    {% endfor %}
  </div>
</div>
