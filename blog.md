---
title: Blog
description: "Below is a list of posts, arranged from the most recent to the oldest. Pagination does not work here due to Jekyll limitations."
thumbnail: "undraw_undraw_posts_givd_-1-_5vi7.svg"
---

## Blog posts

Filter and pagination are not supported for this site, use the `ctrl + f` to find relevant topic. Click cards below to read further.

<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for post in site.posts %}
    <div class="col">
      <div class="card h-100">
        <div class="p-4">
          <img class="card-img-top" src="{{ site.baseurl }}/assets/svgs/{{ post.thumbnail }}" alt="{{ post.thumbnail }}" style="aspect-ratio: 143 / 90;">
        </div>
        <div class="card-body border-top">
          <h2 class="h5 card-title">{{ post.title }}</h2>
          <h3 class="h6 card-subtitle mb-2 text-body-secondary">{{ post.date | date: "%B %d, %Y" }}</h3>
          <p class="card-text text-truncate" style="max-width: 100%;">{{ post.description }}</p>
          <a href="{{ site.baseurl }}{{ post.url }}" class="card-link stretched-link">Continue reading</a>
        </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">An item</li>
    <li class="list-group-item">A second item</li>
    <li class="list-group-item">A third item</li>
  </ul>
      </div>
    </div>
  {% endfor %}
</div>
