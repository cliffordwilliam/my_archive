---
title: Blog
description: "Below is a list of posts, arranged from the most recent to the oldest. Pagination does not work here due to Jekyll limitations."
thumbnail: "undraw_undraw_posts_givd_-1-_5vi7.svg"
---

## Blog posts

Filter and pagination are not supported for this site, use the `ctrl + f` to find relevant topic. Click cards below to read further.

<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for post in site.posts %}
  {% include card.html post=post %}
  {% endfor %}
</div>
