---
title: "GitHub Pages and Jekyll"
date: 2024-09-12 22:49:21 -0000
thumbnail: undraw_website_5bo8.svg
description: "Create static site with GitHub Pages and Jekyll."
reading_time: "0:22 mins:secs"
tags: 
  - "Web development"
---

## Introduction

Everything you need to know is from <a href="https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll" target="_blank">GitHub Docs</a> and from <a href="https://jekyllrb.com/" target="_blank">Jekyll</a>. Summary, GitHub Pages is powered by Jekyll. Work locally with Jekyll opinionated way, on git push event GitHub by default runs Jekyll build process that turns your repo content into only HTML files. Jekyll build process does the manual repetitive HTML writing for you, use Jekyll features to define layout once or store variables so you do not write them multiple times in multiple pages.

## GitHub Pages & Jekyll

### Who can use this?

GitHub Pages is available for public repos with GitHub Free (and the free one for organizations). GitHub Pages uses GitHub Actions for Jekyll build by default (bypass with .nojekyll file in root).

### About GitHub Pages and Jekyll

Jekyll is a static site generator with built-in support for GitHub Pages. Jekyll turns Markdown, HTML and Liquid (templating language) files into a static site made only out of static HTML site. Jekyll is not officially supported for Windows, no need to setup Jekyll locally, we can use the GitHub Jekyll build instead. Downside is we cannot see the build unless we push to GitHub. You can use other static site generator or edit the build action or build in another servertoo, but we will not cover any of that here.

### Jekyll configuration

`_config.yml` in project root is the Jekyll settings file. Refer <a href="https://jekyllrb.com/docs/configuration/" target="_blank">Jekyll configuration doc</a>. There are some settings that cannot be edited when using GitHub Pages Jekyll. There are folders and files that Jekyll does not build based on their names too (you can force it if you want), see the details on this yourself we do not need to know any of this to make this site.

### Front matter

Add YAML Front Matter to the top of Markdown or HTML files to add metadata to it like page.title. Refer <a href="https://jekyllrb.com/docs/front-matter/" target="_blank">Jekyll Front Matter doc</a>. When using GitHub with Jekyll, you get `site.github` property, refer <a href="https://jekyll.github.io/github-metadata/site.github/" target="_blank">Jekyll Metadata doc</a>.

### Theme

There are existing themes that are supported by GitHub but we will not be using that here. Read on that detail yourself.

### Plugins

GitHub Jekyll has some plugins out of the box, you can also add extra if you want. We will not cover this as well.

## Creating a repository for your site

### Create a repo

Name your repo (all lower case in kebab case), you can either create a user or organization site like `<user>.github.io` or `<organization>.github.io`. Set it to public since private ones are not availbale for free ones. Here we use neither, we make our own repo name, you can name it whatever you want.

You can change the publishing source to a different branch dedicated for this site but here we use the main branch, or you can use a certain dir dedicated for this site source files. If you do want to change it there are further configuration that you need to do in GitHub then you should read <a href="https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site" target="_blank">Configuring a publishing source for your GitHub Pages site.</a>.

Edit the `_config.yml` like this:

<pre><code># if you want to force HTTPS, specify the domain without the http at the start, e.g. example.com
domain: "cliffordwilliam.github.io"

# the base hostname and protocol for your site, e.g. http://example.com
url: "https://cliffordwilliam.github.io"

# place folder name if the site is served in a subfolder
baseurl: "/my_archive"
</code></pre>

In the above, since we use neither user or organization repo, then we need to set the baseurl. We will use that property whenever we want to declare hyperlinks.

You can commit and push. Here we want to first setup this remote repo to publish the site. Go to said repo URL / Settings / Pages. There you need to set main branch and save it.

In the rare occasion that the build fail, re running the build usually puts you in a indefinite queue (you are stuck in limbo since you do not have permission to stop the queue). When that happens you want to do the following:

<pre><code>git commit --amend --no-edit
git push --force-with-lease
</code></pre>

That will **create a new commit (even if you did not change anything)**. Then the next one force a push where it **overwrite the old commit**.

## Adding content

TODO

## Important things

- GitHub Pages is available for public repos with GitHub Free (and the free one for organizations)
- Bypass Jekyll build with .nojekyll file in root
- Jekyll is not officially supported for Windows
- Organization owner can restrict GitHub Pages publications
- There are some settings that cannot be edited when using GitHub Pages Jekyll
- There are folders and files that Jekyll does not build based on their names too (you can force it if you want)
- When using GitHub with Jekyll, you get `site.github` property, access your repo metadata with it
- Only some themes are supported with GitHub Pages Jekyll
- GitHub Pages Jekyll has some plugins out of the box
- Name your repo (all lower case in kebab case), you can either create a user or organization site like `<user>.github.io` or `<organization>.github.io`
- If build fail and it says invalid token (even if you do not use that), then amend commit and force push it to force a new build queue