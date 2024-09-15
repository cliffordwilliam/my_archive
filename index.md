---
title: "Home"  
description: "Welcome! This archive contains the knowledge I've gathered throughout my life."  
thumbnail: "undraw_undraw_undraw_undraw_undraw_website_o7n3_bucy_30uo_-1-_d6br_0qfo.svg"
---

## Introduction

Welcome to my personal knowledge archive, a place where I store and share everything I’ve learned over the years. This site serves as a central hub for all the valuable information I've discovered online and in life. Instead of hunting for references scattered across the web, I’ve gathered and reworded them here for quick and easy access.

You can explore my [blog]({% link _collection/blog.html %}) to dive into the complete collection of posts or browse the [tags]({% link _collection/tags.html %}) to see topics organized by category. If you’d like to know more about me, feel free to visit the [about]({% link _collection/about.html %}).

To know how this site was built, [visit GitHub Pages and Jekyll blog]({% link _posts/2024-09-12-github-pages-and-jekyll.md %}) to learn how to make one yourself for free.

All vector illustrations on this site are courtesy of [undraw.co](https://undraw.co/){:target="_blank"}. I love using vector images because they scale perfectly to any size, and Undraw has a vast collection of illustrations to choose from. Images help me associate ideas better—especially when it comes to recalling information. For the site’s styling, I’m using [Bootstrap](https://getbootstrap.com/){:target="_blank"}. While I could design my own CSS, Bootstrap saves me time by handling accessibility and cross-browser compatibility, which is why I prefer it. The design might be simple, but as long as it’s clean and easy to read, it works for me.

<h2 class="mt-5">Latest post</h2>

Here's the most recent blog post:

<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for post in site.posts limit:1 %}
  {% include card.html post=post %}
  {% endfor %}
</div>
