---
layout: home
title: Welcome
---

# Welcome to my blog 👋

This is my personal blog hosted on **GitHub Pages** using Jekyll.

Check out my posts below ⬇️
## Recent Posts

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      - <span>{{ post.date | date: "%Y-%m-%d" }}</span>
    </li>
  {% endfor %}
</ul>