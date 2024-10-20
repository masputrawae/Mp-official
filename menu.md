---
layout: default
title: Menu
description: "Halaman menu untuk semua kategori dan artikel."
---

# Menu Artikel

Selamat datang di halaman menu! Di sini Anda dapat menemukan semua artikel yang telah saya tulis, diorganisasikan berdasarkan kategori.

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

## Daftar Artikel

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
