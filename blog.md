---
title: Blog Posts
---

Below is a list of posts, arranged from the most recent to the oldest.

<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for post in site.posts %}
    <div class="col">
      <div class="card h-100">
        <div class="card-body p-4 d-flex flex-column">
          <h3 class="card-title mb-0">{{ post.title }}</h3>
          <small class="text-body-secondary mb-1">{{ post.date | date: "%B %d, %Y" }}</small>
          <p class="card-text mb-auto">{{ post.excerpt | strip_html }}</p>
          <a href="{{ post.url | relative_url }}" class="icon-link gap-1 icon-link-hover stretched-link">
            Continue reading
          </a>
        </div>
      </div>
    </div>
  {% endfor %}
</div>
