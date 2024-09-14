---
title: Tags
description: "Below is a list of posts organized under their tags, arranged from the most recent to the oldest. Pagination does not work here due to Jekyll limitations."
thumbnail: "undraw_choose_color_uotg.svg"
---

## Tags

Blog posts are categorized under certain tags. Filter and pagination are not supported for this site, use the `ctrl + f` to find relevant topic. Click cards below to read further.

{% for tag in site.tags %}
  <div class="py-5">
    <h3 id="{{ tag[0] | slugize }}" class="pb-2 border-bottom">{{ tag[0] }}</h3>
    <div class="row row-cols-1 row-cols-md-3 g-4 py-5">
      {% for post in tag[1] %}
      {% include card.html post=post %}
      {% endfor %}
    </div>
  </div>
{% endfor %}