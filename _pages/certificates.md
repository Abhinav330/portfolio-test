---
layout: single
title: "Certificates"
permalink: /certificates/
---

<style>
  /* 📌 Container for certificates - Adjusts layout on different screens */
  .certificate-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    padding: 20px;
  }

  /* 📌 Individual Certificate Cards */
  .certificate-card {
    width: 22%;  /* Adjust width for better fit */
    background: #222;
    border-radius: 10px;
    overflow: hidden;
    text-align: center;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease-in-out;
  }

  /* 📌 Hover Effect */
  .certificate-card:hover {
    transform: scale(1.05);
  }

  /* 📌 Certificate Image */
  .certificate-card img {
    width: 100%;
    height: auto;
    max-height: 180px;
    object-fit: cover;
    border-bottom: 2px solid #fff;
  }

  /* 📌 Certificate Title */
  .certificate-title {
    color: #fff;
    font-size: 16px;
    font-weight: bold;
    padding: 10px;
  }

  /* 📌 View Button */
  .certificate-button {
    display: block;
    width: 90%;
    margin: 10px auto;
    padding: 10px;
    background: #ff4500;
    color: white;
    text-align: center;
    font-size: 14px;
    font-weight: bold;
    border-radius: 5px;
    text-decoration: none;
    transition: background 0.3s ease-in-out;
  }

  .certificate-button:hover {
    background: #ff5722;
  }

  /* 📌 RESPONSIVE DESIGN - Mobile & Tablet Optimization */
  @media (max-width: 1024px) {  /* For tablets */
    .certificate-card {
      width: 30%;
    }
  }

  @media (max-width: 768px) {  /* For mobile screens */
    .certificate-card {
      width: 45%;
    }
  }

  @media (max-width: 480px) {  /* For small mobile screens */
    .certificate-card {
      width: 90%;
    }
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
