---
title: "Academic Research"
layout: academic-research
permalink: /academic-research/
---

## 📚 My Academic Research Papers

Explore my research work. Click on any title to read the full report.

{% for research in site.academic-research %}
  <div class="research-card">
    <h2 class="research-title">
      <a href="{{ research.url | relative_url }}">{{ research.title }}</a>
    </h2>
    <p class="research-description">{{ research.description }}</p>
  </div>
{% endfor %}
