---
layout: single
title: "Certificates"
permalink: /certificates/
---

<style>
  .certificate-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    padding: 20px;
  }
  
  .certificate-card {
    width: 25%;
    background: #222;
    border-radius: 10px;
    overflow: hidden;
    text-align: center;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease-in-out;
  }

  .certificate-card:hover {
    transform: scale(2.0);
  }

  .certificate-card img {
    width: 120%;
    height: 150px;
    object-fit: cover;
    border-bottom: 2px solid #fff;
  }

  .certificate-title {
    color: #fff;
    font-size: 16px;
    font-weight: bold;
    padding: 10px;
  }

  .certificate-button {
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

  .certificate-button:hover {
    background: #ff5722;
  }
</style>

<div class="certificate-container">
  {% for certificate in site.certificates %}
    <div class="certificate-card">
      {% if certificate.image contains "://" %}
        <img src="{{ certificate.image }}" alt="{{ certificate.title }}">
      {% else %}
        <img src="{{ certificate.image | prepend: site.baseurl | prepend: site.url }}" alt="{{ certificate.title }}">
      {% endif %}
      <div class="certificate-title">{{ certificate.title }}</div>
      <a href="{{ certificate.link }}" class="certificate-button" target="_blank">View</a>
    </div>
  {% endfor %}
</div>
