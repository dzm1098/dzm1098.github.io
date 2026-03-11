---
layout: page
title: Photography
permalink: /photography/
description: Selected photography work.
nav: true
nav_order: 2
---

{% assign featured_photo_names = "2.jpg|DSC02777.jpg|6.jpg" | split: "|" %}
{% assign photo_files = site.static_files | where_exp: "file", "file.path contains '/assets/img/photography/'" | sort: "path" %}

<div class="projects">
  <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
    {% for featured_name in featured_photo_names %}
      {% for photo in photo_files %}
        {% assign ext = photo.extname | downcase %}
        {% assign is_generated_webp = false %}
        {% if photo.name contains "-480.webp" or photo.name contains "-800.webp" or photo.name contains "-1400.webp" %}
          {% assign is_generated_webp = true %}
        {% endif %}
        {% if photo.name == featured_name %}
          {% if is_generated_webp == false %}
            {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" or ext == ".gif" %}
              <div class="col">
                <div class="card hoverable">
                  <img
                    src="{{ photo.path | relative_url }}"
                    class="card-img-top"
                    alt="{{ photo.basename | replace: '-', ' ' | replace: '_', ' ' }}"
                    loading="lazy"
                    data-zoomable
                  >
                </div>
              </div>
            {% endif %}
          {% endif %}
        {% endif %}
      {% endfor %}
    {% endfor %}
  </div>

  <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4 mt-1">
    {% for photo in photo_files %}
      {% assign ext = photo.extname | downcase %}
      {% assign is_generated_webp = false %}
      {% if photo.name contains "-480.webp" or photo.name contains "-800.webp" or photo.name contains "-1400.webp" %}
        {% assign is_generated_webp = true %}
      {% endif %}
      {% unless featured_photo_names contains photo.name %}
        {% if is_generated_webp == false %}
          {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" or ext == ".gif" %}
            <div class="col">
              <div class="card hoverable">
                <img
                  src="{{ photo.path | relative_url }}"
                  class="card-img-top"
                  alt="{{ photo.basename | replace: '-', ' ' | replace: '_', ' ' }}"
                  loading="lazy"
                  data-zoomable
                >
              </div>
            </div>
          {% endif %}
        {% endif %}
      {% endunless %}
    {% endfor %}
  </div>
</div>
