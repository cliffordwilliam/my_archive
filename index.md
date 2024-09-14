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

## Latest post

<div class="card w-100">
    <div class="p-4">
        <img class="card-img-top" src="{{ site.baseurl }}/assets/svgs/{{ site.posts.first.thumbnail }}" alt="{{ site.posts.first.thumbnail }}"
        style="width: 100%; height: 180px; object-fit: cover;">
    </div>
    <div class="card-body">
        <h2 class="h5 card-title">{{ site.posts.first.title }}</h2>
        <h3 class="h6 card-subtitle mb-2 text-body-secondary">{{ site.posts.first.date | date: "%B %d, %Y" }}</h3>
        <p class="card-text text-truncate" style="max-width: 100%;">{{ site.posts.first.description }}</p>
        <a href="{{ site.baseurl }}{{ site.posts.first.url }}" class="btn btn-primary">Continue reading</a>
    </div>
    <ul class="list-group list-group-flush">
      <div class="card-header">
        Tags
      </div>
      {% for tag in site.posts.first.tags %}
      <li class="list-group-item">
        <a class="card-link" href="{{site.baseurl}}/tags.html#{{tag|slugize}}">{{tag}}</a>
      </li>
      {% endfor %}
    </ul>
</div>