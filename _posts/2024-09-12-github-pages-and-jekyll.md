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

For comprehensive information, refer to the [GitHub Docs](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll) and [Jekyll's official site](https://jekyllrb.com/). GitHub Pages uses Jekyll as its static site generator. When you push changes to GitHub, it automatically triggers the Jekyll build process, converting your repository content into static HTML files. Jekyll simplifies the creation of static sites by handling repetitive HTML writing for you. It allows you to define layouts once and use variables, so you don’t have to repeat content across multiple pages.

## GitHub Pages & Jekyll

### Who Can Use This?

GitHub Pages is available for public repositories with GitHub Free and for free organization accounts. By default, GitHub Pages uses GitHub Actions for Jekyll builds. You can bypass this with a `.nojekyll` file in the root of your repository.

### About GitHub Pages and Jekyll

Jekyll is a static site generator that integrates seamlessly with GitHub Pages. It transforms Markdown, HTML, and Liquid (a templating language) files into a static site composed solely of HTML. Jekyll is not officially supported on Windows, so you don’t need to set it up locally; GitHub handles the Jekyll build process for you. Note that you won’t see the build output until you push to GitHub. While you can use other static site generators or custom build actions, we’ll focus on Jekyll here.

### Jekyll Configuration

The `_config.yml` file in your project root contains Jekyll’s settings. For details, refer to the [Jekyll Configuration Documentation](https://jekyllrb.com/docs/configuration/). Some settings are not editable when using GitHub Pages’ built-in Jekyll. Additionally, certain folders and files are ignored by Jekyll based on their names (though you can force inclusion if necessary). You don’t need to delve into these details to set up your site.

### Front Matter

Add YAML Front Matter to the top of your Markdown or HTML files to include metadata like `page.title`. For more information, see the [Jekyll Front Matter Documentation](https://jekyllrb.com/docs/front-matter/). When using GitHub Pages with Jekyll, you also have access to the `site.github` property. For details, refer to the [Jekyll Metadata Documentation](https://jekyll.github.io/github-metadata/site.github/).

### Theme

GitHub offers several supported themes, but we won’t be using them here. For more information, you can explore the available themes on GitHub.

### Plugins

GitHub’s Jekyll setup includes some built-in plugins, and you can add additional ones if needed. However, we won’t cover plugins in this guide.

## Creating a Repository for Your Site

### Create a Repository

Name your repository using all lowercase letters and kebab-case (e.g., `my-repo`). You can create a user or organization site with names like `<user>.github.io` or `<organization>.github.io`, but you can also choose any other name. Make sure to set the repository to public, as private repositories are not available with the free plan.

You can configure GitHub Pages to use a different branch or directory for your site’s source files. If you want to change these settings, refer to [Configuring a Publishing Source for Your GitHub Pages Site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

Update the `_config.yml` file as follows:

```yaml
# If you want to force HTTPS, specify the domain without the http at the start, e.g., example.com
domain: "cliffordwilliam.github.io"

# The base hostname and protocol for your site, e.g., http://example.com
url: "https://cliffordwilliam.github.io"

# Specify the folder name if the site is served in a subfolder
baseurl: "/my_archive"
```

Since we are not using a user or organization repository, you need to set the `baseurl` property. Use this property when declaring hyperlinks.

Commit and push your changes. To publish your site, go to the repository URL > Settings > Pages. Set the main branch as the publishing source and save the changes.

If the build fails and you encounter an indefinite queue, you can try:

```bash
git commit --amend --no-edit
git push --force-with-lease
```

This creates a new commit (even if unchanged) and force pushes it, replacing the old commit.

## Adding Content

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