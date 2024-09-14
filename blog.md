---
title: Blog
description: "Browse all posts, from latest to oldest. Note: This site uses GitHub Pages and Jekyll pagination isn't supported on GitHub Pages."
thumbnail: "undraw_undraw_posts_givd_-1-_5vi7.svg"
---

## Blog posts

To explore each post, click the **Continue reading** button below the preview. Since pagination isn't available on GitHub Pages, instead you can quickly find specific posts by using `ctrl + f` to search for keywords. Alternatively, visit the [blog page]({{ site.baseurl }}{{ site.data.navigation.navigations[1].url }}) to see all posts from newest to oldest.

<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for post in site.posts %}
  {% include card.html post=post %}
  {% endfor %}
</div>
