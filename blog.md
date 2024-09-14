---
title: Blog
description: "Browse all posts, from latest to oldest. Note: Pagination isn't supported on GitHub Pages."
thumbnail: "undraw_undraw_posts_givd_-1-_5vi7.svg"
---

## Blog posts

To explore each post, click the **continue reading** button below the preview. Since pagination isn't available on GitHub Pages, you can quickly find specific posts by using <code>&lt;ctrl + f&gt;</code> to search for keywords. Alternatively, visit the [tags page]({{ site.baseurl }}{{ site.data.navigation.navigations[2].url }}) to filter posts by tags and browse them from newest to oldest.

<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for post in site.posts %}
  {% include card.html post=post %}
  {% endfor %}
</div>
