---
layout: single
title: "Projects"
permalink: /projects/
---

<style>
/* Project Container */
.project-container {
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 20px;
}

/* Project Card Layout */
.project-card {
    display: flex;
    align-items: center;
    background: #1c1c1c;
    padding: 15px;
    border-radius: 10px;
    border: 2px solid #333;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
}

/* Project Image - 10% */
.project-image {
    width: 10%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.project-image img {
    max-width: 100%;
    height: auto;
    border-radius: 8px;
}

/* Project Info - 80% */
.project-info {
    width: 80%;
    padding: 0 15px;
    text-align: left;
}

.project-title {
    color: #4aa0ff;
    font-size: 20px;
    font-weight: bold;
}

.project-description {
    color: #bbb;
    font-size: 14px;
}

/* Project Buttons - 10% */
.project-buttons {
    width: 10%;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
}

.btn {
    text-decoration: none;
    padding: 8px 12px;
    border-radius: 6px;
    font-weight: bold;
    text-align: center;
    display: inline-block;
    width: 100%;
}

.btn-primary {
    background: #4aa0ff;
    color: white;
}

.btn-secondary {
    background: #bbb;
    color: black;
}
</style>

<div class="project-container">
  {% for project in site.projects %}
    <div class="project-card">
      <div class="project-image">
        {% if project.image contains "://" %}
          <img src="{{ project.image }}" alt="{{ project.title }}">
        {% else %}
          <img src="{{ project.image | prepend: site.baseurl | prepend: site.url }}" alt="{{ project.title }}">
        {% endif %}
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
</div>
