---
title: Blog
description: "Browse all posts, from latest to oldest."
thumbnail: "undraw_undraw_posts_givd_-1-_5vi7.svg"
---

## Blog posts

Below is a list of all posts arranged from the most recent to the oldest. Each post is displayed as a card. To read a post, click **Continue reading** on the card. You can also filter posts by clicking on any of the card **tags**. 

Due to GitHub Pages and Jekyll limitations, pagination is not available. To find a specific topic, use <kbd>Ctrl</kbd> + <kbd>F</kbd> to search within the page. Alternatively, you can visit the [tags]({{ site.baseurl }}{% link tags.md %}) page to see all posts, organized from newest to oldest, by their tags.

<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for post in site.posts %}
  {% include card.html post=post %}
  {% endfor %}
</div>
