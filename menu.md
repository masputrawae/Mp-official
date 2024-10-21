---
layout: default
title: Menu
description: "Halaman menu untuk semua kategori dan artikel."
---

# Menu Artikel

Selamat datang di halaman menu! Di sini Anda dapat menemukan semua artikel yang telah saya tulis, diorganisasikan berdasarkan kategori.

# Artikel Terbaru

<div class="grid-container">
  {% for post in site.posts | limit: 3 %}
    <div class="card">
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p>{{ post.excerpt }}</p>
      <small>{{ post.date | date: "%B %d, %Y" }}</small>
    </div>
  {% endfor %}
</div>
<style>
  .grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 20px;
  }
  .card {
    border: 1px solid #ddd;
    padding: 20px;
    border-radius: 10px;
    background-color: #E5000000;
  }
  .card h3 {
    margin-top: 0;
  }
</style>

## Kategori

<ul>
  {% for category in site.categories %}
    <li>{{ category[0] }}
      <ul>
        {% for post in category[1] %}
          <li>
            <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
          </li>
        {% endfor %}
      </ul>
    </li>
  {% endfor %}
</ul>
