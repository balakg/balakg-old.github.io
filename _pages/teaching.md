---
layout: default
title: teaching
permalink: /teaching/
description: Courses I have taught or assisted with.
nav: true
nav_order: 2
---
<div class="post">
  <header class="post-header">
    <h1 class="post-title">{{ page.title }}</h1>
    <p class="post-description">{{ page.description }}</p>
  </header>

  <article>
    {% if site.teaching_categories %}
    <div class="inline-list text-center">
      {% for category in site.teaching_categories %}
        <button class="btn btn-sm z-depth-0" data-filter=".{{ category | slugify }}">{{ category }}</button>
      {% endfor %}
    </div>
    {% endif %}

    <div class="projects">
      <div class="grid">
        {% assign teaching = site.teaching | sort: "importance" %}
        {% for course in teaching %}
          <div class="grid-item {{ course.category | slugify }}">
            <a href="{% if course.external_url %}{{ course.external_url }}{% else %}{{ course.url | relative_url }}{% endif %}" {% if course.external_url %}target="_blank"{% endif %}>
              <div class="card hoverable">
                {% if course.img %}
                  {% include figure.html path=course.img alt=course.title class="card-img-top" %}
                {% endif %}
                <div class="card-body">
                  <h2 class="card-title">{{ course.title }}</h2>
                  <p class="card-text">{{ course.description }}</p>
                </div>
              </div>
            </a>
          </div>
        {% endfor %}
      </div>
    </div>
  </article>
</div>
