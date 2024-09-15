---
title: Tags
description: "Browse all posts organized by their tags, from latest oldest."
thumbnail: "undraw_choose_color_uotg.svg"
---

## Tags

Below is a list of all posts organized by their tags, arranged from the most recent to the oldest. Each post is displayed as a card, To read a post, click **Continue reading** on the card. You can also filter posts by clicking on any of the card **tags**.

Due to GitHub Pages and Jekyll limitations, pagination is not available. To find a specific topic, use <kbd>Ctrl</kbd> + <kbd>F</kbd> to search within the page. Alternatively, you can visit the [blog]({{ site.baseurl }}{% link blog.md %}) page to see all posts, organized from newest to oldest.

{% for tag in site.tags %}
  <div class="py-5">
    <h3 id="{{ tag[0] | slugize }}" class="pb-2 border-bottom mt-0">{{ tag[0] }}</h3>
    <div class="row row-cols-1 row-cols-md-3 g-4 py-5">
      {% for post in tag[1] %}
      {% include card.html post=post %}
      {% endfor %}
    </div>
  </div>
{% endfor %}