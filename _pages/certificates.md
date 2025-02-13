---
layout: single
title: "Certificates"
permalink: /certificates/
---

<h2>My Certifications</h2>

{% for certificate in site.certificates %}
  <div class="certificate">
    <h3><a href="{{ certificate.url }}">{{ certificate.title }}</a></h3>
    <p><strong>Issued by:</strong> {{ certificate.issuer }}</p>
    <p><strong>Date:</strong> {{ certificate.date | date: "%B %d, %Y" }}</p>
    {% if certificate.link %}
      <p><a href="{{ certificate.link }}" target="_blank">View Certificate</a></p>
    {% endif %}
    <hr>
  </div>
{% endfor %}
