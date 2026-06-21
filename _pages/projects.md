---
layout: page
title: projects
permalink: /projects/
description: This page gives an overview on my ongoing and past projects.
nav: true
nav_order: 3
display_categories: [computational history of science and knowledge, critical digital humanities, book projects, alchemy, past]
horizontal: false
---

<--
# Habilitation project on Computational History of Science
In my habilitation project, I investigate computational methods for the history of science, examining early modern knowledge organisation resources through a range of computational methods and corpora. The project consists of three main strands. 
1. The first focuses on language and dictionaries.
2. The second explores computer vision approaches for early modern technical compendia and handbooks.
3. The third investigates recipes as repositories of practical, embodied, and collective knowledge. This part involves the in silico (.ie. computationaly chemistry) replication of alchemical recipes. 

The recently appeared *Ambix* special issue that I co-edited forms part of this broader research agenda. --> 

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
