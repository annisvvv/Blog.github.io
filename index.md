---
layout: page
title: "My Blog"
---

This is my personal blog. You can find more information about me in the [[about]] section.

I wish to you a good lecture.
 
#### Posts:

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      - <span>{{ post.date | date: "%Y-%m-%d" }}</span>
    </li>
  {% endfor %}
</ul>
