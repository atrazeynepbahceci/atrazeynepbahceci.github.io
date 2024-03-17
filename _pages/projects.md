---
layout: page
title: projects
permalink: /projects/
description: Notable projects completed at Istanbul Technical University & Sabanci University.
nav: true
nav_order: 1
horizontal: false
---
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}"><h2 class="category">{{ category }}</h2></a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <div class="container">
    <div class="row">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% endfor %}
{% else %}
{% assign sorted_projects = site.projects | sort: "importance" %}
  <div class="container">
    <div class="row">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
{% endif %}
</div>
