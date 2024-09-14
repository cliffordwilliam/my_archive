---
title: Blog
---

Below is a list of posts, arranged from the most recent to the oldest. Pagination does not work here due to Jekyll limitations.

<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for post in site.posts %}
    <div class="col">
      <div class="card h-100">
        <div class="p-4">
          <img class="card-img-top" src="{{ site.baseurl }}/assets/svgs/{{ post.thumbnail }}" alt="{{ post.thumbnail }}" style="width: 286px; height: 180px; object-fit: cover;">
        </div>
        <div class="card-body border-top">
          <h2 class="h5 card-title">{{ post.title }}</h2>
          <h3 class="h6 card-subtitle mb-2 text-body-secondary">{{ post.date | date: "%B %d, %Y" }}</h3>
          <p class="card-text">{{ post.excerpt | strip_html }}</p>
          <a href="{{ post.url | relative_url }}" class="card-link stretched-link">Continue reading</a>
        </div>
      </div>
    </div>
  {% endfor %}
</div>
