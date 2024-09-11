---
title: Blog Posts
---

## Blog Posts List

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <br>
      Published on: {{ post.date | date: "%B %d, %Y" }}
      <br>
      <p>{{ post.excerpt | strip_html }}</p>
    </li>
  {% endfor %}
</ul>
