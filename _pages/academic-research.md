---
layout: single
title: "Academic Research"
permalink: /academic-research/
---

<style>
  .research-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    padding: 20px;
  }
  
  .research-card {
    width: 45%;
    background: #222;
    border-radius: 10px;
    overflow: hidden;
    text-align: center;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease-in-out;
    padding-bottom: 10px;
  }

  .research-card:hover {
    transform: scale(1.05);
  }

  .research-card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    border-bottom: 2px solid #fff;
  }

  .research-title {
    color: #fff;
    font-size: 18px;
    font-weight: bold;
    padding: 10px;
  }

  .research-button {
    display: block;
    width: 80%;
    margin: 10px auto;
    padding: 8px;
    background: #ff4500;
    color: white;
    text-align: center;
    font-size: 14px;
    border-radius: 5px;
    text-decoration: none;
    transition: background 0.3s ease-in-out;
  }

  .research-button:hover {
    background: #ff5722;
  }
</style>

<div class="research-container">
  {% for research in site.academic-research %}
    <div class="research-card">
      {% if research.image contains "://" %}
        <img src="{{ research.image }}" alt="{{ research.title }}">
      {% else %}
        <img src="{{ research.image | prepend: site.baseurl | prepend: site.url }}" alt="{{ research.title }}">
      {% endif %}
      <div class="research-title">{{ research.title }}</div>
      <a href="{{ research.url }}" class="research-button">Read More</a>
    </div>
  {% endfor %}
</div>
