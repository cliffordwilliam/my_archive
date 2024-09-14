---
title: Tags
description: "Below is a list of posts organized under their tags, arranged from the most recent to the oldest. Pagination does not work here due to Jekyll limitations."
thumbnail: "undraw_undraw_posts_givd_-1-_5vi7.svg"
---

## Tags

Blog posts are categorized under certain tags. Filter and pagination are not supported for this site, use the `ctrl + f` to find relevant topic. Click cards below to read further.

{% for tag in site.tags %}
  <div class="py-5">
    <h3 id="#{{ tag | slugize }}" class="pb-2 border-bottom">{{ tag[0] }}</h3>
    <div class="row row-cols-1 row-cols-md-3 g-4 py-5">
      {% for post in tag[1] %}
          <div class="col">
            <div class="card h-100">
              <div class="p-4">
                <img class="card-img-top" src="{{ site.baseurl }}/assets/svgs/{{ post.thumbnail }}" alt="{{ post.thumbnail }}" style="aspect-ratio: 143 / 90;">
              </div>
              <div class="card-body border-top">
                <h2 class="h5 card-title">{{ post.title }}</h2>
                <h3 class="h6 card-subtitle mb-2 text-body-secondary">{{ post.date | date: "%B %d, %Y" }}</h3>
                <p class="card-text text-truncate" style="max-width: 100%;">{{ post.description }}</p>
                <a href="{{ site.baseurl }}{{ post.url }}" class="btn btn-primary">Continue reading</a>
              </div>
              <ul class="list-group list-group-flush">
                <div class="card-header">
                  Tags
                </div>
                {% for tag in post.tags %}
                  <li class="list-group-item">
                    <a class="card-link" href="{{site.baseurl}}/tags.html#{{tag|slugize}}">{{tag}}</a>
                  </li>
                {% endfor %}
              </ul>
            </div>
          </div>
      {% endfor %}
    </div>
  </div>
{% endfor %}