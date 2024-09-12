---
title: Blog Posts
---

## Blog Posts List

Write body here

<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for post in site.posts %}
    <div class="col">
      <div class="card h-100">
        <div class="card-body">
          <h5 class="card-title">{{ post.title }}</h5>
          <p class="card-text">{{ post.excerpt | strip_html }}</p>
          <a href="{{ post.url | relative_url }}" class="btn btn-primary stretched-link">Read more</a>
        </div>
        <div class="card-footer">
          <small class="text-body-secondary">Published on: {{ post.date | date: "%B %d, %Y" }}</small>
        </div>
      </div>
    </div>
  {% endfor %}
</div>

<div class="row row-cols-1 row-cols-md-3 g-4">
</div>