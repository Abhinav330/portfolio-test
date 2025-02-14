---
layout: research-list
title: "Academic Research"
permalink: /portfolio-test/academic-research/
---

## 📚 My Academic Research Papers

Explore my research work. Click on any title to read the full report.

<div class="research-container">
  {% for research in site.academic-research %}
    <div class="research-card">
      <img src="{{ research.image | prepend: site.baseurl }}" alt="{{ research.title }}">
      <div class="research-title">{{ research.title }}</div>
      <a href="{{ research.url | relative_url }}" class="research-button">Read More</a>
    </div>
  {% endfor %}
</div>
