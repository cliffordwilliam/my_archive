---
title: "Home"
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <br>
      Published on: {{ post.date | date: "%B %d, %Y" }}
      <br>
      Categories: {{ post.categories | join: ", " }}
      <br>
      Tags: {% for tag in post.tags %} <a href="/tag/{{ tag }}">{{ tag }}</a> {% unless forloop.last %}, {% endunless %} {% endfor %}
    </li>
  {% endfor %}
</ul>
