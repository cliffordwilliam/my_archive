---
title: Blog Posts
---

<h1>Blog Posts</h1>

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <br>
      Published on: {{ post.date | date: "%B %d, %Y" }}
      <br>
      Categories: {{ post.categories | join: ", " }}
      <br>
      Tags: {% for tag in post.tags %} <a href="/tag/{{ tag }}">{{ tag }}</a>{% unless forloop.last %}, {% endunless %} {% endfor %}
      <br>
      <p>{{ post.excerpt | strip_html }}</p>  <!-- Displaying the excerpt -->
    </li>
    <hr>
  {% endfor %}
</ul>
