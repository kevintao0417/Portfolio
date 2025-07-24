---
layout: page
title: Experience
permalink: /experience/
description: A summary of my professional experience.
nav: true
nav_order: 4
display_categories: [Intern]
horizontal: false
---

<!-- pages/experience.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized experiences -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_experiences = site.experience | where: "category", category %}
  {% assign sorted_experiences = categorized_experiences | sort: "importance" %}
  <!-- Generate cards for each experience -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for experience in sorted_experiences %}
      {% include experience_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for experience in sorted_experiences %}
      {% include experience.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display experiences without categories -->

{% assign sorted_experiences = site.experience | sort: "importance" %}

  <!-- Generate cards for each experience -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for experience in sorted_experiences %}
      {% include experience_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for experience in sorted_experiences %}
      {% include experience.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
