---
title: "Home"  
description: "Welcome! This archive contains the knowledge I've gathered throughout my life."  
thumbnail: "undraw_undraw_undraw_undraw_undraw_website_o7n3_bucy_30uo_-1-_d6br_0qfo.svg"
---

## Introduction

Welcome to my personal knowledge archive, where I store and share everything I’ve learned over the years. This site serves as a central hub for the valuable information I’ve gathered throughout my life. Instead of tracking down scattered references, I’ve curated and reworded them here for quick and easy access. The content is organized into posts, much like a blog. I chose this structure because it’s simple and effective for managing content.

You can explore my [blog]({{ site.baseurl }}{% link blog.md %}) to dive into the complete collection of posts or browse the [tags]({{ site.baseurl }}{% link tags.md %}) to find posts by topic. If you'd like to know more about me or the site, feel free to visit the [about]({{ site.baseurl }}{% link about.md %}) page. To visit the GitHub repository for this site, click **GitHub** in the hero header. If you'd like to download the repository as a `.zip` or `.tar.gz` file, click **Download** in the hero header.

I'm really happy with how this site turned out. I’ve even written a guide on how to build a similar site in my [GitHub Pages and Jekyll post]({{ site.baseurl }}{% post_url 2024-09-12-github-pages-and-jekyll %}). The guide is accessible to everyone, even those without a programming background. One of the great benefits of building a site like this is the freedom to customize everything—the structure, appearance, and functionality for free, with optional costs like domain names or additional services.

A quick overview of the site: it’s powered by Jekyll on GitHub Pages, which comes with a few limitations, such as no pagination and no option to highlight specific lines in code snippets. The vector illustrations are from [unDraw](https://undraw.co/), which I love because vector images scale perfectly without losing quality. Most of the CSS is from [Bootstrap](https://getbootstrap.com/), which makes handling cross-browser compatibility and accessibility easier. I’ve made a few minor tweaks to improve the user experience, but nothing major. While the design is minimal, I believe it keeps everything clean and functional.

<h2 class="mt-5">Latest post</h2>

Here's the most recent blog post:

<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for post in site.posts limit:1 %}
  {% include card.html post=post %}
  {% endfor %}
</div>
