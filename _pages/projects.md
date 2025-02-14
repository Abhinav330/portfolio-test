---
layout: single
title: "Projects"
permalink: /projects/
---

<style>
/* 📌 Project Container - Adjusts Layout on Different Devices */
.project-container {
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 20px;
}

/* 📌 Project Card - Now Uses Flexbox for Responsive Layout */
.project-card {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    background: #1c1c1c;
    padding: 15px;
    border-radius: 10px;
    border: 2px solid #333;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
    transition: transform 0.2s ease-in-out;
}

.project-card:hover {
    transform: scale(1.02);
}

/* 📌 Image Section - Adjusts to Fit Different Screens */
.project-image {
    flex: 1;
    min-width: 150px;
    max-width: 20%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.project-image img {
    width: 100%;
    height: auto;
    border-radius: 8px;
}

/* 📌 Project Info - Adjusts Width Dynamically */
.project-info {
    flex: 2;
    min-width: 250px;
    padding: 0 15px;
    text-align: left;
}

/* 📌 Title & Description */
.project-title {
    color: #4aa0ff;
    font-size: 20px;
    font-weight: bold;
}

.project-description {
    color: #bbb;
    font-size: 14px;
}

/* 📌 Buttons Section - Now Responsive */
.project-buttons {
    flex: 1;
    min-width: 150px;
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

/* 📌 RESPONSIVE DESIGN - Ensures It Looks Good on Mobile */
@media (max-width: 768px) {
    .project-card {
        flex-direction: column;
        text-align: center;
    }
    
    .project-image {
        max-width: 80%;
    }

    .project-info {
        max-width: 100%;
    }

    .project-buttons {
        width: 100%;
        flex-direction: row;
        justify-content: center;
    }

    .btn {
        width: auto;
        padding: 10px 16px;
    }
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
