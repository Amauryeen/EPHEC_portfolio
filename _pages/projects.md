---
layout: page
title: activities
permalink: /projects/
description: A collection of extracurricural activities I've done during my studies.
nav: true
nav_order: 3
display_categories: [challenges, courses, volunteers, projects, workshops]
horizontal: true
---

<table style="width:100%;">
<tr><th>activity</th><th>theme</th><th>valued hours</th><th>real hours</th></tr>
<tr><td><a href="/projects/activity_1">Cyber Security Challenge 2023</a></td><td>Cybersecurity</td><td>10</td><td>32</td></tr>
<tr><td><a href="/projects/activity_2">Cyber Security Challenge 2024</a></td><td>Cybersecurity</td><td>10</td><td>30</td></tr>
<tr><td><a href="/projects/activity_3">Getting started with React</a></td><td>Development</td><td>8</td><td>8</td></tr>
<tr><td><a href="/projects/activity_4">Create your first website with Wordpress 6</a></td><td>Development</td><td>10</td><td>11</td></tr>
<tr><td><a href="/projects/activity_5">CHE2</a></td><td>Social</td><td>10</td><td>~250</td></tr>
<tr><td><a href="/projects/activity_6">Supervising a Capture The Flag</a></td><td>Systems</td><td>2.5</td><td>2.5</td></tr>
<tr><td><a href="/projects/activity_7">Creating a Capture The Flag</a></td><td>Systems</td><td>10</td><td>~12</td></tr>
<tr><td><a href="/projects/activity_8">Discussion on artificial intelligence and the uses of ChatGPT</a></td><td>AI</td><td>1</td><td>1</td></tr>
<tr><td><a href="/projects/activity_9">A playful approach to electronics</a></td><td>Electronics</td><td>1</td><td>1</td></tr>
<tr><td><a href="/projects/activity_10">Learning to weld</a></td><td>Electronics</td><td>1</td><td>1</td></tr>
<tr><td><a href="/projects/activity_11">Microcontroller programming</a></td><td>Electronics</td><td>1</td><td>1</td></tr>
<tr><td>‎</td><td></td><td></td><td></td></tr>
<tr><td><b>totals</b></td><td></td><td><b>64.5</b></td><td><b>~349.5</b></td></tr>
</table>

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
