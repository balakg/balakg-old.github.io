---
layout: page
title: teaching
permalink: /teaching/
description: Courses I have taught or am currently teaching.
nav: true
nav_order: 4
---

<div class="projects">
  {% if site.teaching %}
    <div class="grid">
      {% assign teaching = site.teaching | sort: 'importance' %}
      {% for course in teaching %}
        {% include projects.html %}
      {% endfor %}
    </div>
  {% else %}
    <p>No courses listed yet.</p>
  {% endif %}
</div>
