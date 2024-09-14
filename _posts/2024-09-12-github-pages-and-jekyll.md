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

Had to edit the css that i got here to add padding else wont work even if you link another css after this one

post that tried the right way
https://talk.jekyllrb.com/t/rouge-code-snippet-highlighting-not-working/121

post that tried the right way
https://talk.jekyllrb.com/t/canonical-way-to-use-syntax-highlighting-of-code-blocks/4645

link for css for highlight
https://frankindev.com/2017/03/18/syntax-highlight-with-rouge-in-jekyll/

## Important Considerations

- **Availability**: GitHub Pages is accessible for public repositories with GitHub Free, including the free tier for organizations.
- **Bypassing Jekyll**: To bypass the Jekyll build process, place a `.nojekyll` file in the root of your repository.
- **Windows Support**: Jekyll is not officially supported on Windows, so you don’t need to set it up locally if using GitHub Pages.
- **Restrictions**: Organization owners can restrict GitHub Pages publications.
- **Configuration Limitations**: Some settings cannot be modified when using GitHub Pages’ default Jekyll setup.
- **Ignored Files**: Jekyll ignores certain folders and files based on their names, though you can force their inclusion if necessary.
- **Metadata**: When using GitHub with Jekyll, the `site.github` property provides access to your repository’s metadata.
- **Themes**: Only certain themes are supported with GitHub Pages’ Jekyll integration.
- **Plugins**: GitHub Pages’ Jekyll setup includes some built-in plugins.
- **Repository Naming**: Name your repository using lowercase letters and kebab-case (e.g., `<user>.github.io` or `<organization>.github.io`). You can also use other names for personal repositories.
- **Build Failures**: If the build fails and reports an invalid token (even if you haven't used one), amend your commit and force push to trigger a new build queue.
