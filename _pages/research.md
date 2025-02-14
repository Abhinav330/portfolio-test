---
layout: research-list
title: "Academic Research"
permalink: /research/
---

## 📚 Research Papers

{% for paper in site.research %}
  <div class="research-card">
    <h2><a href="{{ paper.url | prepend: site.baseurl }}">{{ paper.title }}</a></h2>
    <p>{{ paper.date | date: "%B %d, %Y" }}</p>
    <p>{{ paper.description }}</p>
  </div>
{% endfor %}
