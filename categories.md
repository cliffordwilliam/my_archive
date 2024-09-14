---
title: Categories
description: "Below is a list of posts organized under their categories, arranged from the most recent to the oldest. Pagination does not work here due to Jekyll limitations."
thumbnail: "undraw_undraw_posts_givd_-1-_5vi7.svg"
---

## Blog posts

Filter and pagination are not supported for this site, use the `ctrl + f` to find relevant topic. Click cards below to read further.

{% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}