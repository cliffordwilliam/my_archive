---
title: "Home"  
description: "Welcome! This archive contains the knowledge I've gathered throughout my life."  
thumbnail: "undraw_undraw_undraw_undraw_undraw_website_o7n3_bucy_30uo_-1-_d6br_0qfo.svg"
---

## Introduction

Welcome to my personal knowledge archive, a place where I store and share everything I’ve learned over the years. This site serves as a central hub for all the valuable information I've discovered online and in life. Instead of hunting for references scattered across the web, I’ve gathered and reworded them here for quick and easy access.

You can explore my [blog]({{ site.baseurl }}{{ site.data.navigation.navigations[1].url }}) to dive into the complete collection of posts or browse the [tags]({{ site.baseurl }}{{ site.data.navigation.navigations[2].url }}) to see topics organized by category. If you’d like to know more about me, feel free to visit the [about page]({{ site.baseurl }}{{ site.data.navigation.navigations[3].url }}).

{% assign specific_post = site.posts | where: "title", "GitHub Pages and Jekyll" | first %}
To know how this site was built, [visit GitHub Pages and Jekyll blog]({{ site.baseurl }}{{ specific_post.url }}) to learn how to make one yourself for free.

All vector illustrations on this site are courtesy of [undraw.co](https://undraw.co/). I love using vector images because they scale perfectly to any size, and Undraw has a vast collection of illustrations to choose from. Images help me associate ideas better—especially when it comes to recalling information. For the site’s styling, I’m using [Bootstrap](https://getbootstrap.com/). While I could design my own CSS, Bootstrap saves me time by handling accessibility and cross-browser compatibility, which is why I prefer it. The design might be simple, but as long as it’s clean and easy to read, it works for me.

## Latest post

Here's the most recent blog post:

{% assign latest_post = site.posts | first %}
{% assign latest_post_list = latest_post | push: latest_post %}
{% include card.html posts=latest_post_list %}