---
layout: single
title: "Projects"
permalink: /projects/
---

<style>
  .project-container {
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 20px;
  }

  .project-card {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: #222;
    padding: 15px;
    border-radius: 10px;
    border: 2px solid #333;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease-in-out;
  }

  .project-card:hover {
    transform: scale(1.03);
  }

  .project-image img {
    width: 120px;
    height: 120px;
    border-radius: 8px;
    object-fit: cover;
  }

  .project-info {
    flex: 1;
    padding: 0 15px;
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

  .project-buttons {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .btn {
    text-decoration: none;
    padding: 8px 12px;
    border-radius: 6px;
    font-weight: bold;
    text-align: center;
    display: inline-block;
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
