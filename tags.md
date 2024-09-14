---
title: Tags
description: "Posts here are organized by their tags, arranged from latest to olders. Note: This site uses GitHub Pages and Jekyll pagination isn't supported on GitHub Pages."
thumbnail: "undraw_choose_color_uotg.svg"
---

## Tags

To explore each post, click the **Continue reading** button below the preview. Since pagination isn't available on GitHub Pages, you can quickly find specific posts by using `ctrl + f` to search for keywords. Alternatively, visit the [tags page]({{ site.baseurl }}{{ site.data.navigation.navigations[2].url }}) to filter posts by tags and browse them from newest to oldest.

{% for tag in site.tags %}
  <div class="py-5">
    <h3 id="{{ tag[0] | slugize }}" class="pb-2 border-bottom">{{ tag[0] }}</h3>
    {% include card.html posts=tag[1] %}
  </div>
{% endfor %}