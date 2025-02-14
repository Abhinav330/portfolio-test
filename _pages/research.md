---
layout: research-list
title: "Academic Research"
permalink: /portfolio-test/research/
---

## 📚 Research Papers

<div class="research-container">
  {% for paper in site.research %}
    <div class="research-card">
      <h2><a href="{{ paper.url }}">{{ paper.title }}</a></h2>
      <p>{{ paper.date | date: "%B %d, %Y" }}</p>
      <p>{{ paper.description }}</p>
    </div>
  {% endfor %}
</div>
