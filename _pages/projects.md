---
layout: single
title: "Projects"
permalink: /projects/
---

{% for project in site.projects %}
  <div class="project-card">
    <div class="project-image">
      <img src="{{ project.image | prepend: site.baseurl }}" alt="{{ project.title }}">
    </div>
    <div class="project-info">
      <h2 class="project-title">{{ project.title }}</h2>
      <p class="project-description">{{ project.description }}</p>
    </div>
    <div class="project-buttons">
      <a href="{{ project.live }}" target="_blank" class="btn btn-primary">Use this project</a>
      <a href="{{ project.github }}" target="_blank" class="btn btn-secondary">Code on GitHub</a>
    </div>
  </div>
{% endfor %}
